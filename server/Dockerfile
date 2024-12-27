# 使用 Node.js Alpine 版本作为基础镜像
FROM node:alpine

# 设置工作目录
WORKDIR /app

# 复制 package.json 和 package-lock.json
COPY package*.json ./

# 安装依赖
RUN npm install --production

# 复制应用程序代码
COPY . .

# 暴露应用程序运行的端口
EXPOSE 8081

# 启动应用程序
CMD ["node", "server/index.js"]