# first-time-docker
## การกระทำของ docker ทำได้ด้วยกัน 4 อย่าง
+ 1.container
+ 2.image
+ 3.disk
+ 4.network
    docker container run hello-world
## เช็คว่ามี docker images อะไรบ้าง
    docker images
## ดูว่ามี Volume อะไรบ้าง ?Volume เนื้อที่ disk ใน container
    docker volume ls
## container มี network อะไรบ้าง
# bridge = ต่อกันโดยตรง
# host =  คุยได้ระหว่าง host กับ container เท่านั้น
# none = limit network ไม่ต่อ network 
    docker network ls
# Deployment สร้างเนื้อที่ในการเก็บข้อมูล
    docker volume create portainer_data
# ทำการ run contianer แยกทีละส่วน
+ -d run แล้วจะอยู่ในเครื่องไปเลย
+ -p (ตัวแรก)xpost เข้าไป container ผ่าน ports อะไร portด้านหลังคือของ container 
+ -p (ตัวที่สอง)สร้าง port เรากับ container เชื่อมต่อกัน
+ --name ตั้งชื่อ container ชื่ออะไร
+ --restart=always ถ้าตายเมื่อไหร่ให้ restart ใหม่
+ -v (ตัวแรก) เชื่อม path local กับ container เข้าหากัน
+ -v (ตัวสอง) Volume ที่สร้างให้นำไปใช้ใน container path data แล้วไปโหลดใน images ตามด้วย version
    docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.11.1
* https://localhost:9443/#!/init/admin เข้าไปตั้งค่ารหัสผ่าน