FROM node:16-alpine as builder

WORKDIR /app

COPY manifests ./
COPY packs/packages/             ./packages/

RUN yarn install --immutable
RUN yarn workspace my-app build

# FROM node:16-alpine

# WORKDIR /app

# COPY --from=builder /app/.yarnrc.yml ./.yarnrc.yml
# COPY --from=builder /app/.yarn ./.yarn
# COPY --from=builder /app/.pnp.cjs ./.pnp.cjs
# COPY --from=builder /app/yarn.lock ./yarn.lock
# COPY --from=builder /app/.next ./.next
# COPY --from=builder /app/package.json ./package.json
# COPY --from=builder /app/public ./public


# # Some runtime env here...
# ENV NODE_ENV="production"

# ENV PORT="3000"
# EXPOSE 3000

CMD ["yarn", "workspace", "my-app", "start"]