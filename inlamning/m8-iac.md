## Steg 4

Sophie körde terraform init och sedan terrafomr plan. Hon läste igenom planen. Efter det applicera hon allt med terraform apply.

![](m8-steg4.png)


## Steg 5

Sophie verifiera att nya floating ip:n fungerar. Båda curl kommandon kom tillbaka som status: ok. Frontenden syntes också på webbläsaren med nya ip:n.

![](m8-steg5.png)


## Steg 6

Efter att ha bekräftat att nya ip:n fungerar, gick vi in på instances och raderade m7:ans VM. Sen gick vi till float ips och raderade VM:ens floating ip.

![](m8-steg6a.png)
![](m8-steg6b.png)


## Steg 7

Willem skrev ut terraform state list. Som listar ut allt som terraform bokför.

![](m8-steg7.png)


## Steg 8 

Willem skrev ut ipen för destroy. Sedan destroya han instansen och körde om terrafomr apply. Så skrev han ut ipen igen. 

![](m8-steg8a.png)
![](m8-steg8b.png)