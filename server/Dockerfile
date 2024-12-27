# 构建阶段
FROM node:alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm install --production

COPY . .

# 最终阶段
FROM node:alpine

WORKDIR /app

COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/server ./server
COPY --from=builder /app/package*.json ./

# 暴露端口
EXPOSE 8081

CMD ["node", "server/index.js"]