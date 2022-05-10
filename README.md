# first-time-docker
## การกระทำของ docker ทำได้ด้วยกัน 4 อย่าง
# 1.container
# 2.image
# 3.disk
# 4.network
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
