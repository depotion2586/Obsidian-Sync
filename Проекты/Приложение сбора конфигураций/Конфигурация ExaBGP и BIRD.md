Exa 
### Содержание 
1. [[#Конфигурационный файл ExaBGP в NS Border]]
2. [[#Конфигурационный файл Bird Host VM]]
### Конфигурационный файл ExaBGP NS Border
```
# Конфигурация располагается по пути /etc/exabgp.conf
neighbor 192.0.0.1 {
    # Параметры нашей Border
    router-id 192.0.0.2;
    local-address 192.0.0.2;
    local-as 65002;
    
    # Параметры host VM
    peer-as 65001;
    
    # Фейковые маршруты, передаваемые на хост:
    static {
        route 10.100.100.0/24 next-hop 192.0.0.2;
        route 10.200.200.0/24 next-hop 192.0.0.2;
    }
}
```

### Конфигурационный файл BIRD Host VM
```
# Конфигурационный файл располагается по пути /etc/bird/bird.conf

router id 192.0.0.1;

# Разрешаем BIRD записывать полученные маршруты в ядро Linux хоста
protocol kernel {
    persist;
    scan time 20;
    import all;
    export all;
}

# Отслеживаем локальные интерфейсы
protocol device {
    scan time 10;
}

# Настраиваем BGP-пиринг с Border
protocol bgp Border {
    description "Peering with NS Border";
    local as 65001;
    neighbor 192.0.0.2 as 65002;
    import all;  # Принимать все, что пришлет сосед
    export none; # Host ничего не отправляет соседу
}
```