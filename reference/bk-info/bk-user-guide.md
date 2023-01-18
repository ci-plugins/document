## **BK Getting Started Using Documentation**

## **1. Create a user**

The user information in BK environment can be added, deleted, and checked in "User Management". The following figure shows.

![](../../.gitbook/assets/image-reference-bkuserguide-1.png)


### **1.1 Adding users**
![](../../.gitbook/assets/image-reference-bkuserguide-2.png)

![](../../.gitbook/assets/image-reference-bkuserguide-3.png)

### 1.2 Modify user information

![](../../.gitbook/assets/image-reference-bkuserguide-4.png)

Related study materials.
- document：https://bk.tencent.com/docs/document/6.0/146/7330(This document is the community version, and the enterprise version is basically the same function)

- video：https://ke.qq.com/course/3101748?taid=10600778153546804

## **2. Create a business**

Enter the "Configuration Platform", where you can manage the "Business-Host".

![](../../.gitbook/assets/image-reference-bkuserguide-5.png)

### **2.1 Creating a business**

![](../../.gitbook/assets/image-reference-bkuserguide-6.png)

![](../../.gitbook/assets/image-reference-bkuserguide-7.png)

![](../../.gitbook/assets/image-reference-bkuserguide-8.png)

![](../../.gitbook/assets/image-reference-bkuserguide-9.png)

![](../../.gitbook/assets/image-reference-bkuserguide-10.png)

### **2.2 View the modules and hosts of the business**

![](../../.gitbook/assets/image-reference-bkuserguide-11.png)

![](../../.gitbook/assets/image-reference-bkuserguide-12.png)

如果没有看到刚创建的业务，点击页面左下角的“刷新应用”，再重复「步骤2」、「步骤3」即可
然后就看到我们刚才创建的业务的信息了。

![](../../.gitbook/assets/image-reference-bkuserguide-13.png)

## **3. Create a permission group to associate users with the operation rights of the business in the platform**

Here, you need the admin account to add permissions to the business, in order to facilitate the subsequent operations related to the business, we recommend using "Create permission group", and then associate the "user" to the "permission group ".

![](../../.gitbook/assets/image-reference-bkuserguide-14.png)


### **3.1 Create a "Configuration Platform Template for Business Permissions "**

![](../../.gitbook/assets/image-reference-bkuserguide-15.png)

切换身份后，进入“超级管理员”模式，只有超级管理员可以创建高权限级别的“业务权限组”

![](../../.gitbook/assets/image-reference-bkuserguide-16.png)

![](../../.gitbook/assets/image-reference-bkuserguide-17.png)

![](../../.gitbook/assets/image-reference-bkuserguide-18.png)

后续会推出“对应角色(如：运维、开发)推荐默认配置”的版本，现用版本需要手动勾选
然后为刚才选择的“权限”关联对应的“资源实例”


![](../../.gitbook/assets/image-reference-bkuserguide-19.png)

![](../../.gitbook/assets/image-reference-bkuserguide-20.png)

![](../../.gitbook/assets/image-reference-bkuserguide-21.png)

![](../../.gitbook/assets/image-reference-bkuserguide-22.png)

![](../../.gitbook/assets/image-reference-bkuserguide-23.png)

![](../../.gitbook/assets/image-reference-bkuserguide-24.png)


### **3.2 Create a "business permission group "**

![](../../.gitbook/assets/image-reference-bkuserguide-25.png)

![](../../.gitbook/assets/image-reference-bkuserguide-26.png)

![](../../.gitbook/assets/image-reference-bkuserguide-27.png)

![](../../.gitbook/assets/image-reference-bkuserguide-28.png)

![](../../.gitbook/assets/image-reference-bkuserguide-29.png)

## **4. Add a host for your business**

Go to the home page and click "Node Management".

![](../../.gitbook/assets/image-reference-bkuserguide-30.png)

![](../../.gitbook/assets/image-reference-bkuserguide-31.png)

![](../../.gitbook/assets/image-reference-bkuserguide-32.png)

![](../../.gitbook/assets/image-reference-bkuserguide-33.png)

![](../../.gitbook/assets/image-reference-bkuserguide-34.png)

## **5. Managing hosts in the Configuration Platform**

Next, we will deploy a service called "dataserver" on the newly added host. To make it easier to manage it, we will create some information on the "configuration platform" first.

### **5.1 Create a set (cluster) and module**

![](../../.gitbook/assets/image-reference-bkuserguide-35.png)

![](../../.gitbook/assets/image-reference-bkuserguide-36.png)

![](../../.gitbook/assets/image-reference-bkuserguide-37.png)

![](../../.gitbook/assets/image-reference-bkuserguide-38.png)


### **5.2 Moving hosts to modules and modifying host-related information**

![](../../.gitbook/assets/image-reference-bkuserguide-39.png)

![](../../.gitbook/assets/image-reference-bkuserguide-40.png)

![](../../.gitbook/assets/image-reference-bkuserguide-41.png)

![](../../.gitbook/assets/image-reference-bkuserguide-42.png)

![](../../.gitbook/assets/image-reference-bkuserguide-43.png)

![](../../.gitbook/assets/image-reference-bkuserguide-44.png)



## **6. Deploy dataserver service using "Job Platform"**

![](../../.gitbook/assets/image-reference-bkuserguide-45.png)

### **6.1 Upload local files to the host**

https://www.python.org/ftp/python/3.9.4/Python-3.9.4.tgz

![](../../.gitbook/assets/image-reference-bkuserguide-46.png)

![](../../.gitbook/assets/image-reference-bkuserguide-47.png)

![](../../.gitbook/assets/image-reference-bkuserguide-48.png)

![](../../.gitbook/assets/image-reference-bkuserguide-49.png)


### **6.2 Deploying services using "script execution"**

![](../../.gitbook/assets/image-reference-bkuserguide-50.png)

![](../../.gitbook/assets/image-reference-bkuserguide-51.png)


    cd /data
    yum install -y gcc python39-devel bzip2-devel sqlite-devel openssl-devel readline-devel xz-devel tk-devel gdbm-devel
    
    mkdir -p /data/corefile
    chmod 777 /data/corefile
    echo 'ulimit -c unlimited' >> /etc/profile
    sed -i "/^kernel.core_pattern =/d" /etc/sysctl.conf 
    echo 'kernel.core_pattern = /data/corefile/core_%e_%t' >> /etc/sysctl.conf
    sysctl -p /etc/sysctl.conf
    
    tar zxvf Python-3.9.4.tgz 
    cd Python-3.9.4
    ./configure
    make && make install
    make clean && make distclean
    
    mkdir -p /data/app
    pip3 install Flask
    pip3 freeze > /data/app/requirements.txt
    cat > /data/app/app.py <<EOF
    from flask import Flask
    app = Flask(__name__)
    
    @app.route('/')
    def hello_world():
        return 'Hello, World'
    EOF
    
    cd /data/app
    nohup python3 -m flask run >/dev/null 2>&1 &

## **7. Monitoring hosts and processes using the "Monitoring Platform "**

### **7.1 Create process-related information in the "Configuration Platform "**

![](../../.gitbook/assets/image-reference-bkuserguide-52.png)

![](../../.gitbook/assets/image-reference-bkuserguide-53.png)


### **7.2 Monitoring platform configuration alarms**
![](../../.gitbook/assets/image-reference-bkuserguide-54.png)

![](../../.gitbook/assets/image-reference-bkuserguide-55.png)

![](../../.gitbook/assets/image-reference-bkuserguide-56.png)

![](../../.gitbook/assets/image-reference-bkuserguide-57.png)

![](../../.gitbook/assets/image-reference-bkuserguide-58.png)

![](../../.gitbook/assets/image-reference-bkuserguide-59.png)

![](../../.gitbook/assets/image-reference-bkuserguide-60.png)

![](../../.gitbook/assets/image-reference-bkuserguide-61.png)

