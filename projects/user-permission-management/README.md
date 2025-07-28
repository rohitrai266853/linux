# User and Permission Management

This project demonstrates how to manage users, groups, and permissions in Linux.

---

## Steps

### 1. Create Users

```bash
sudo adduser alice
sudo adduser bob
```

---

### 2. Create Group and Add Users

```bash
sudo groupadd projectteam
sudo usermod -aG projectteam alice
sudo usermod -aG projectteam bob
```

---

### 3. Create Shared Folder

```bash
sudo mkdir /srv/project
sudo chown :projectteam /srv/project
sudo chmod 770 /srv/project
```

---

### 4. Test Access

```bash
su - alice
cd /srv/project
touch testfile_by_alice
exit

su - bob
cd /srv/project
touch testfile_by_bob
exit
```

---

## Result

- Only `alice` and `bob` (members of `projectteam`) can access and write to `/srv/project`.
- Other users have no access.
