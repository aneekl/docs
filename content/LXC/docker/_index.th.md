---
date: 2023-07-09T16:50:16+02:00
title: docker
weight: 20
---

จะใช้ไม่ต้องให้ privileged ก็ได้

    security.privileged: "true"

แต่อย่างน้อยต้องมี nesting

    security.nesting: "true"

ถ้าใช้ไม่ได้อีกก็ใส่นี่เพิ่มไป ทำอะไรก็ไม่รู้ 55555

    raw.lxc: |
      lxc.apparmor.profile=unconfined
      lxc.cgroup.devices.allow=a
      lxc.cap.drop=

จริงๆ มาแค่ security.nesting: "true" อย่างเดียวก็พอแล้ว แต่จะต่อ unix socket ไม่ได้ถ้าไม่มี privileged ใน docker-compose.yaml
