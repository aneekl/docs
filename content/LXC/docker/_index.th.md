---
date: 2023-07-09T16:50:16+02:00
title: docker
weight: 20
---

จะใช้ไม้ต้องให้ privileged ก็ได้

    security.privileged: "true"

แต่อย่างน้อยต้องมี nesting

    security.nesting: "true"

ถ้าใช้ไม่ได้อีกก็ใส่นี่เพิ่มไป ทำอะไรก็ไม่รู้ 55555

    raw.lxc: |
      lxc.apparmor.profile=unconfined
      lxc.cgroup.devices.allow=a
      lxc.cap.drop=

เจอมาอีกว่าใส่ต่างข้างล่างแทนก็ได้
```
security.syscalls.intercept.mknod: "true"
security.syscalls.intercept.setxattr: "true" 
