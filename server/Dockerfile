# 第一阶段：构建阶段
FROM node:16-alpine AS builder

# 设置工作目录
WORKDIR /app

# 复制 package.json 和 package-lock.json 并安装生产依赖
COPY package*.json ./
RUN npm install --production

# 复制应用程序代码
COPY . .

# 第二阶段：运行阶段
FROM node:16-alpine

# 设置工作目录
WORKDIR /app

# 从构建阶段复制 node_modules 和应用程序代码
COPY --from=builder /app .

# 暴露应用程序运行的端口
EXPOSE 8081

# 启动应用程序
CMD ["node", "index.js"]