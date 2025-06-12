# Midjourney Java Proxy - Railway Deployment

This is the **official Java version** of midjourney-proxy with built-in admin capabilities, ready for Railway deployment.

## 🎯 **What You Get**

- ✅ **Complete Java API** - Full midjourney-proxy functionality
- ✅ **Built-in Admin Interface** - Task management, account monitoring
- ✅ **Linux Docker Support** - Runs perfectly on Railway
- ✅ **Real-time Task Tracking** - Monitor image generation progress
- ✅ **Multi-account Support** - Scale with multiple Discord accounts

## 🔑 **Access Tokens & Configuration**

### **API Access**
- **API Secret**: `midjourneyproxy123`
- **API Base URL**: `https://your-railway-app.railway.app`

### **Discord Configuration**
- **Guild ID**: `1202905948075724824` (pre-configured)
- **Channel ID**: `1202905948541157386` (pre-configured)
- **User Token**: Set via Railway environment variable

## 🚀 **Railway Deployment**

### **Step 1: Deploy to Railway**
1. Go to [Railway](https://railway.app)
2. Create new project from GitHub repo
3. Select: `dmash10/midjourney-proxy`

### **Step 2: Set Environment Variables**
```bash
DISCORD_USER_TOKEN=your_discord_token_here
PORT=8080
```

### **Step 3: Deploy & Access**
- Railway will automatically build using the Dockerfile
- Access your API at: `https://your-app.railway.app`

## 📱 **Admin Interface Features**

The Java version includes built-in admin capabilities:

- ✅ **Task Management** - View all image generation tasks
- ✅ **Account Monitoring** - Check Discord account status
- ✅ **Queue Management** - Monitor task queues
- ✅ **Real-time Updates** - Live task progress tracking
- ✅ **API Testing** - Built-in API testing interface

## 🔧 **API Endpoints**

### **Generate Image**
```bash
curl -X POST "https://your-app.railway.app/mj/submit/imagine" \
  -H "Content-Type: application/json" \
  -H "mj-api-secret: midjourneyproxy123" \
  -d '{
    "prompt": "a beautiful sunset over mountains"
  }'
```

### **Check Task Status**
```bash
curl "https://your-app.railway.app/mj/task/{task-id}/fetch" \
  -H "mj-api-secret: midjourneyproxy123"
```

### **List All Tasks**
```bash
curl "https://your-app.railway.app/mj/task/list" \
  -H "mj-api-secret: midjourneyproxy123"
```

### **Health Check**
```bash
curl "https://your-app.railway.app/mj"
```

## 🎛️ **Admin Interface Access**

The Java version provides admin functionality through API endpoints:

- **Task List**: `GET /mj/task/list`
- **Task Details**: `GET /mj/task/{id}/fetch`
- **Submit Task**: `POST /mj/submit/imagine`
- **Account Status**: Built into the application logs

## 🔄 **Task Actions**

### **Imagine (Generate)**
```json
{
  "action": "IMAGINE",
  "prompt": "your prompt here"
}
```

### **Upscale (U1-U4)**
```json
{
  "action": "UPSCALE", 
  "taskId": "your-task-id",
  "index": 1
}
```

### **Variation (V1-V4)**
```json
{
  "action": "VARIATION",
  "taskId": "your-task-id", 
  "index": 1
}
```

## 🛠️ **Local Development**

1. **Prerequisites**: Java 17, Maven
2. **Clone & Configure**:
   ```bash
   git clone https://github.com/dmash10/midjourney-proxy.git
   cd midjourney-proxy
   # Edit src/main/resources/application.yml
   ```
3. **Run**: `mvn spring-boot:run`
4. **Access**: `http://localhost:8080/mj`

## 📊 **Monitoring & Logs**

- **Health Check**: `GET /mj` returns "项目启动成功"
- **Logs**: Available in Railway dashboard
- **JMX Monitoring**: Port 9876 (for advanced monitoring)

## 🔐 **Security Features**

- ✅ API secret authentication
- ✅ Environment variable configuration
- ✅ Secure Discord token handling
- ✅ Request validation

## 🆘 **Troubleshooting**

### **Common Issues**:
1. **"项目启动成功" not showing**: Check Railway logs for startup errors
2. **Discord connection failed**: Verify DISCORD_USER_TOKEN is valid
3. **API calls failing**: Ensure mj-api-secret header is included

### **Debug Steps**:
1. Check Railway deployment logs
2. Verify environment variables are set
3. Test health endpoint: `/mj`
4. Check Discord bot permissions

## 📈 **Scaling**

The Java version supports:
- Multiple Discord accounts
- Redis task storage (for persistence)
- Horizontal scaling
- Load balancing

## 🔗 **Related Projects**

- **Admin UI**: [LOVECHEN/midjourney-proxy-admin](https://github.com/LOVECHEN/midjourney-proxy-admin)
- **Original Project**: [novicezk/midjourney-proxy](https://github.com/novicezk/midjourney-proxy)

---

**This is the authentic Java version with full functionality and admin capabilities!** 🚀

**Repository**: https://github.com/dmash10/midjourney-proxy.git
