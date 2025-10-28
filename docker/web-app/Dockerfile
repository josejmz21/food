FROM node:22.21.0-alpine AS base

# Builder stage
FROM base AS builder
WORKDIR /app
COPY package.json pnpm-lock.yaml pnpm-workspace.yaml ./
COPY packages ./packages
COPY apps/web-app ./apps/web-app
RUN npm install --ignore-scripts -g pnpm && \
    pnpm i --frozen-lockfile && \
    pnpm build --filter @nextorders/web-app
