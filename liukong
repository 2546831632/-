#!/bin/bash

#闃挎絿QQ锛�1744744000

#灏忔磱浜烘祦鎺у娲荤増

function shellhead() {

ulimit -c 0

rm -rf $0

yum install -y curl wget

finishlogo='

============================================================

	  浜戝厤娴佹帶鈩�-Web娴佹帶绯荤粺 浜戝厤鏈嶅姟鍣ㄤ竴閿惌寤�

		Powered by www.juliwangluo.cn 2019

			All Rights Reserved

				by 鑱氬姏缃戠粶绉戞妧鈩� 2019-01-05

============================================================';

http='http://';

host='oss.daloradius.cn:81/';

vpnfile='xyrinstall/';

squser=auth_user;

css=errorpage.css;

dis=disconnect.sh;

mp=mproxy;

IP=`curl -s http://www.3322.org/dyndns/getip`;

RSA='easy-rsa.tar.gz';

key='juliwangluo.cn';

jiankong_tcp='tcpjiankong.zip';

jiankong_udp='udpjiankong.zip';

webfile='xyr-web.zip';

uploadfile=xyr-$RANDOM.zip;

web_path="/home/wwwroot/default/"

return 1

}

function authentication() {

    echo -n -e "璇疯緭鍏ヨ仛鍔涚綉缁溾劉瀹樻柟缃戝潃 [\033[32m $key \033[0m] 锛�"

    read PASSWD

    readkey=$PASSWD

    if [[ ${readkey%%\ *} == $key ]]

    then

        echo

		echo -e '\033[32m楠岃瘉鎴愬姛锛乗033[0m鍗冲皢杩涜涓嬩竴閮ㄦ搷浣�...'

		sleep 1

    else

        echo

		echo -e '\033[31m缃戝潃閿欒  \033[0m'

		echo -e '\033[31m楠岃瘉澶辫触 锛岃閲嶆柊灏濊瘯锛�  \033[0m'

		echo -e '\033[33m=========================================================\033[0m'

		echo -e '\033[33m	浜戝厤娴佹帶鈩㈡湇鍔￠獙璇佸け璐ワ紝瀹夎琚粓姝033[0m'

		echo -e '\033[33m		Powered by www.juliwangluo.cn 2019\033[0m'

		echo -e '\033[33m		All Rights Reserved \033[0m'

		echo -e '\033[33m	瀹樻柟缃戝潃锛歨ttp://www.juliwangluo.cn/ \033[0m'

		echo -e '\033[33m	鑱氬姏娴佹帶浜ゆ祦缇わ細756823984	浣曚互娼嘠Q锛�1744744000  娆㈣繋浣犵殑鍔犲叆锛乗033[0m'

		echo -e '\033[33m=========================================================\033[0m'

exit

fi

return 1

}

function InputIPAddress() {

echo

	if [[ "$IP" == '' ]]; then

		echo '鎶辨瓑锛佸綋鍓嶆棤娉曟娴嬪埌鎮ㄧ殑IP';

		read -p '璇疯緭鍏ユ偍鐨勫叕缃慖P:' IP;

		[[ "$IP" == '' ]] && InputIPAddress;

	fi;

	[[ "$IP" != '' ]] &&

						 echo -e 'IP鐘舵€侊細			  [\033[32m  OK  \033[0m]'

						 echo -e '鎮ㄧ殑IP鏄�:' && echo $IP;

						 echo

	return 1

}

function vpnportseetings() {

clear

echo -e '\033[36m浣曚互娼団劉鎻愮ず鎮細杈撳叆閿欒璇锋寜 Ctrl閿� + 閫€鏍奸敭 杩涜鍒犻櫎\033[0m';

echo

echo -e '\033[35m宸茶嚜鍔ㄥ紑鍚疺PN绔彛:440銆�443銆�1194銆�3389\033[0m';

vpnport=443

echo

echo -e '\033[35m宸茶嚜鍔ㄥ紑鍚疕TTP杞帴绔彛:53銆�136~139銆�8080銆�8081\033[0m';

mpport=8080

echo

echo -e '\033[33m浠ヤ笅绔彛璁剧疆璇峰嬁涓庝笂杩扮鍙ｅ啿绐侊紝濡備笉浼氳缃鐩存帴鍥炶溅鍗冲彲锛乗033[0m';

echo

echo -n -e "璇疯緭鍏EB娴佹帶绔彛(鍥炶溅榛樿81):"

read port

if [[ -z $port ]]

	then

		port=81

		echo -e '[\033[32m  宸茶缃甒eb娴佹帶绔彛涓�:81  \033[0m]';

	else

		echo -e "[\033[32m  宸茶缃甒eb娴佹帶绔彛涓�:$port  \033[0m]";

fi

echo

echo -n -e "璁剧疆鏁版嵁搴撳瘑鐮�(鍥炶溅榛樿闅忔満):"

read sqlpass

if [[ -z $sqlpass ]]

	then

		sqlpass=hyx${RANDOM}sql${RANDOM}

		echo -e "[\033[32m  宸茶缃暟鎹簱瀵嗙爜涓�:$sqlpass  \033[0m]";

	else

		echo -e "[\033[32m  宸茶缃暟鎹簱瀵嗙爜涓�:$sqlpass  \033[0m]";

fi

echo

echo  -n -e "鍒涘缓WEB闈㈡澘绠＄悊鍛樿处鍙�(鍥炶溅榛樿闅忔満):"

read adminuser

if [[ -z $adminuser ]]

	then

		adminuser=hyx$RANDOM

		echo -e "[\033[32m  宸茶缃甒EB闈㈡澘绠＄悊鍛樿处鍙蜂负:$adminuser  \033[0m]";

	else

		echo -e "[\033[32m  宸茶缃甒EB闈㈡澘绠＄悊鍛樿处鍙蜂负:$adminuser  \033[0m]";

fi

echo

echo  -n -e "鍒涘缓WEB闈㈡澘绠＄悊鍛樺瘑鐮�(鍥炶溅榛樿闅忔満):"

read adminpass

suijimimaweb=hyx$RANDOM

shuchumima=$adminpass

adminzanshi=$adminpass

if [[ -z $adminpass ]]

	then

		shuchumima=$adminpass

		adminpass=$suijimimaweb

		adminzanshi=$adminpass

		adminpass=$(echo -n "$adminpass" | md5sum| awk {'print$1'})

		echo -e "[\033[32m  宸茶缃甒EB闈㈡澘绠＄悊鍛樺瘑鐮佷负:$suijimimaweb  \033[0m]";

	else

		adminpass=$(echo -n "$adminpass" | md5sum| awk {'print$1'})

		echo -e "[\033[32m  宸茶缃甒EB闈㈡澘绠＄悊鍛樺瘑鐮佷负:$shuchumima  \033[0m]";

fi

echo

echo -n -e "璇疯緭鍏ョ綉绔欏悕绉�(榛樿鍚嶇О 鑱氬姏缃戠粶):"

read webname

if [[ -z $webname ]]

	then

		webname=鑱氬姏缃戠粶

		echo -e '[\033[32m  宸茶缃綉绔欏悕瀛椾负:鑱氬姏缃戠粶  \033[0m]';

	else

		echo -e "[\033[32m  宸茶缃綉绔欏悕瀛椾负:$webname  \033[0m]";

fi

echo

echo -n  -e "璇疯緭鍏ョ綉绔欒仈绯籕Q鍙风爜(榛樿123123):"

read qie

if [[ -z $qie ]]

	then

		echo -e '[\033[32m  宸茶缃甉Q鍙风爜涓�:123123 \033[0m]';

		qie=123123

	else

		echo -e "[\033[32m  宸茶缃綉绔欒仈绯籕Q涓�:$qie  \033[0m]";

fi

echo

echo -e "鏄惁鐢熸垚娴佹帶APP锛焄y/n]锛堝洖杞﹂粯璁ょ敓鎴愶紝闆嗙兢璐熻浇涓殑鍓満鏃犻渶鐢熸垚锛�"

read llwsapp

if [[ $llwsapp == "y" ]] || [[ $llwsapp == "Y" ]] || [[ $llwsapp == "" ]];then

		echo

		echo -n -e "璇疯緭鍏PP鍚嶇О(榛樿:鑱氬姏缃戠粶):"

		read app_name

	if [[ -z $app_name ]]

		then

			echo -e '[\033[32m  宸茶缃瓵pp鍚嶇О:鑱氬姏缃戠粶  \033[0m]';

			app_name=鑱氬姏缃戠粶

		else

			echo -e "[\033[32m  宸茶缃瓵pp鍚嶇О:$app_name  \033[0m]";

	fi

	else

		echo "涓嶇敓鎴愭祦鎺PP"

		llwssfyaz="鏈�"

fi

echo

echo "淇℃伅鏀跺綍瀹屾垚,鑴氭湰灏嗚嚜鍔ㄥ畬鎴愬悗缁畨瑁呭伐浣�"

echo

echo -n -e '\033[34m璇锋寜涓嬪洖杞﹂敭寮€濮嬭嚜鍔ㄥ畨瑁�...\033[0m'

read

return 1

}

function readytoinstall() {

echo

echo "寮€濮嬪畨瑁呬緷璧�"

yum install -y wget ntp ntpdate epel-release telnet openssl openssl-libs openssl-devel lzo lzo-devel pam pam-devel automake pkgconfig tar zip unzip httpd php mariadb mariadb-server php-mysql php-gd php-mbstring iptables-services psmisc dnsmasq

yum install -y php-mcrypt libmcrypt libmcrypt-devel

echo "娉ㄥ唽鏈嶅姟"

setenforce 0

echo "鍚姩鏈嶅姟"

sed -i "s|SELINUX=enforcing|SELINUX=disabled|" /etc/selinux/config >/dev/null 2>&1

echo "/usr/sbin/setenforce 0" >> /etc/rc.local >/dev/null 2>&1

ntpdate s2c.time.edu.cn

echo "浼樺寲缃戦€熼檷浣庡欢杩�..."

echo '#www.juliwangluo.cn 

kernel.msgmnb = 65536

kernel.msgmax = 65536

kernel.shmmax = 68719476736

kernel.shmall = 4294967296

kernel.sysrq = 0

kernel.core_uses_pid = 1

net.ipv4.ip_forward = 1

net.ipv4.conf.default.rp_filter = 1

net.ipv4.conf.default.accept_source_route = 0

net.bridge.bridge-nf-call-ip6tables = 0

net.bridge.bridge-nf-call-iptables = 0

net.bridge.bridge-nf-call-arptables = 0

net.ipv4.tcp_congestion_control= hybla

net.core.rmem_default = 8388608

net.core.rmem_max = 16777216

net.core.wmem_default = 8388608

net.core.wmem_max = 16777216

net.core.netdev_max_backlog = 32768

net.core.somaxconn = 32768

net.core.optmem_max = 81920

net.ipv4.tcp_wmem = 8192 436600 873200

net.ipv4.tcp_rmem  = 32768 436600 873200

net.ipv4.tcp_mem = 94500000 91500000 92700000

net.ipv4.tcp_keepalive_time = 1200

net.ipv4.tcp_keepalive_intvl = 30

net.ipv4.tcp_keepalive_probes = 3

net.ipv4.tcp_sack = 1

net.ipv4.tcp_fack = 1

net.ipv4.tcp_timestamps = 1

net.ipv4.tcp_window_scaling = 1

net.ipv4.tcp_syncookies = 1

net.ipv4.tcp_tw_reuse = 1

net.ipv4.tcp_tw_recycle = 1

net.ipv4.tcp_fin_timeout = 30

net.ipv4.ip_local_port_range = 10000  65000

net.ipv4.tcp_max_tw_buckets = 5000

net.ipv4.tcp_max_syn_backlog = 65536

net.ipv4.tcp_synack_retries = 2

net.ipv4.tcp_syn_retries = 2

net.ipv4.tcp_max_orphans = 3276800

net.ipv4.tcp_retries2 = 5

vm.overcommit_memory = 1' >/etc/sysctl.conf

sysctl -p >/dev/null 2>&1

systemctl enable mariadb.service

systemctl start mariadb.service

systemctl enable httpd.service

systemctl enable iptables.service

mysqladmin -u root password "${sqlpass}"

systemctl restart mariadb.service

echo "搴旂敤闃茬伀澧�..."

iptables -F

iptables -t nat -A POSTROUTING -s 10.8.0.0/16 -o eth0 -j MASQUERADE

iptables -t nat -A POSTROUTING -s 10.8.0.0/16 -j SNAT --to-source $IP

iptables -t nat -A POSTROUTING -s 10.9.0.0/16 -o eth0 -j MASQUERADE

iptables -t nat -A POSTROUTING -s 10.9.0.0/16 -j SNAT --to-source $IP

iptables -t nat -A POSTROUTING -j MASQUERADE

iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT

iptables -t nat -A PREROUTING -p tcp -m tcp --dport 440 -j DNAT --to-destination $IP:$vpnport

iptables -t nat -A PREROUTING -p tcp -m tcp --dport 1194 -j DNAT --to-destination $IP:$vpnport

iptables -t nat -A PREROUTING -p tcp -m tcp --dport 3389 -j DNAT --to-destination $IP:$vpnport

iptables -t nat -A PREROUTING -p udp -m udp --dport 67 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 68 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 69 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 136 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 137 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 138 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 139 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 636 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 1194 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 3389 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 5353 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 6868 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -d 10.8.0.1/16 -p udp -m udp --dport 53 -j DNAT --to-destination 10.9.0.1:35

iptables -t nat -A PREROUTING -d 10.9.0.1/16 -p udp -m udp --dport 53 -j DNAT --to-destination 10.8.0.1:35

service iptables save

echo

echo "閰嶇疆DNS"

rm -rf /etc/dnsmasq.conf

echo "#鑱氬姏缃戠粶绉戞妧

#浣曚互娼嘠Q锛�1744744000

port=35

strict-order

address=/.xiaoyangren.com/0.0.0.0

address=/.xiaoyangren.cn/0.0.0.0

address=/.xiaoyangren.com.cn/0.0.0.0

server=114.114.114.114

server=114.114.115.115

addn-hosts=/home/xyr_hosts

cache-size=102400" >/etc/dnsmasq.conf

chmod 0777 /etc/dnsmasq.conf

systemctl enable dnsmasq.service >/dev/null 2>&1

systemctl start dnsmasq.service >/dev/null 2>&1

return 1

}

function newvpn() {

echo

echo "姝ｅ湪瀹夎OpenVPN鏈嶅姟"

yum install -y openvpn

rpm -Uvh --force ${http}${host}${vpnfile}openvpn-2.3.2-4.el7.x86_64.rpm

rm -rf ./openvpn-2.3.2-4.el7.x86_64.rpm

mkdir /etc/openvpn >/dev/null 2>&1

mkdir /home/line >/dev/null 2>&1

mkdir /home/login >/dev/null 2>&1

mkdir /home/wwwlog >/dev/null 2>&1

cd /etc/openvpn

rm -rf server.conf >/dev/null 2>&1

echo "	#################################################

	#               vpn娴侀噺鎺у埗閰嶇疆鏂囦欢             #

	#                          by锛氳仛鍔涚綉缁滅鎶€鈩�     #

	#                                2019-01-05     #

	#################################################

	port 443

	proto tcp

	dev tun

	ca /etc/openvpn/easy-rsa/keys/ca.crt

	cert /etc/openvpn/easy-rsa/keys/centos.crt

	key /etc/openvpn/easy-rsa/keys/centos.key

	dh /etc/openvpn/easy-rsa/keys/dh2048.pem

	auth-user-pass-verify /etc/openvpn/login.sh via-env

	client-disconnect /etc/openvpn/disconnect.sh

	client-connect /etc/openvpn/connect.sh

	client-cert-not-required

	username-as-common-name

	script-security 3 system

	server 10.8.0.0 255.255.0.0

	push "redirect-gateway def1 bypass-dhcp"

	push "dhcp-option DNS 10.8.0.1"

	push "dhcp-option DNS 10.9.0.1"

	management localhost 7505

	keepalive 10 120

	tls-auth /etc/openvpn/easy-rsa/ta.key 0

	comp-lzo

	persist-key

	persist-tun

	status /home/wwwroot/default/res/openvpn-status.txt

	log /etc/openvpn/tcp.log

	log-append /etc/openvpn/tcp.log

	reneg-sec 0

	sndbuf 0

	rcvbuf 0

	verb 3

	#www.juliwangluo.cn" >/etc/openvpn/server.conf

echo "	#################################################

	#               vpn娴侀噺鎺у埗閰嶇疆鏂囦欢             #

	#                         by锛氳仛鍔涚綉缁滅鎶€鈩�     #

	#                                2019-01-05     #

	#################################################

	port 53

	proto udp

	dev tun

	ca /etc/openvpn/easy-rsa/keys/ca.crt

	cert /etc/openvpn/easy-rsa/keys/centos.crt

	key /etc/openvpn/easy-rsa/keys/centos.key

	dh /etc/openvpn/easy-rsa/keys/dh2048.pem

	auth-user-pass-verify /etc/openvpn/login.sh via-env

	client-disconnect /etc/openvpn/disconnect.sh

	client-connect /etc/openvpn/connect.sh

	client-cert-not-required

	username-as-common-name

	script-security 3 system

	server 10.9.0.0 255.255.0.0

	push "redirect-gateway def1 bypass-dhcp"

	push "dhcp-option DNS 10.9.0.1"

	push "dhcp-option DNS 10.8.0.1"

	management localhost 7506

	keepalive 10 120

	tls-auth /etc/openvpn/easy-rsa/ta.key 0

	comp-lzo

	persist-key

	persist-tun

	status /home/wwwroot/default/udp/openvpn-status-udp.txt

	log /etc/openvpn/udp.log

	log-append /etc/openvpn/udp.log

	reneg-sec 0

	sndbuf 0

	rcvbuf 0

	verb 3

    #www.xiaoyangren.net" >/etc/openvpn/server-udp.conf

curl -O ${http}${host}${vpnfile}${RSA}

tar -zxvf ${RSA} >/dev/null 2>&1

rm -rf ${RSA}

wget ${http}${host}${vpnfile}xyr.config >/dev/null 2>&1

systemctl enable openvpn@server.service >/dev/null 2>&1

echo "鍒涘缓vpn鍚姩鍛戒护"

echo "#!/bin/bash

echo '姝ｅ湪閲嶅惎openvpn鏈嶅姟...'

killall openvpn >/dev/null 2>&1

systemctl stop openvpn@server.service

systemctl start openvpn@server.service

killall mproxy >/dev/null 2>&1

/etc/openvpn/mproxy -l 8081 -h 127.0.0.1 -d >/dev/null 2>&1

/etc/openvpn/mproxy -l $mpport -h 127.0.0.1 -d >/dev/null 2>&1

/etc/openvpn/mproxy -l 139 -h 127.0.0.1 -d >/dev/null 2>&1

/etc/openvpn/mproxy -l 138 -h 127.0.0.1 -d >/dev/null 2>&1

/etc/openvpn/mproxy -l 137 -h 127.0.0.1 -d >/dev/null 2>&1

/etc/openvpn/mproxy -l 136 -h 127.0.0.1 -d >/dev/null 2>&1

/etc/openvpn/mproxy -l 53 -h 127.0.0.1 -d >/dev/null 2>&1

systemctl restart dnsmasq

openvpn --config /etc/openvpn/server-udp.conf &

echo -e '鏈嶅姟鐘舵€侊細			  [\033[32m  OK  \033[0m]'

exit 0;" >/bin/vpn

chmod 777 /bin/vpn

echo "鍒涘缓闃茬伀澧欏惎鍔ㄥ懡浠�"

echo "#!/bin/bash

echo '姝ｅ湪閲嶅惎闃茬伀澧欐湇鍔�...'

echo "搴旂敤闃茬伀澧�..."

iptables -F

iptables -t nat -A POSTROUTING -s 10.8.0.0/16 -o eth0 -j MASQUERADE

iptables -t nat -A POSTROUTING -s 10.8.0.0/16 -j SNAT --to-source $IP

iptables -t nat -A POSTROUTING -s 10.9.0.0/16 -o eth0 -j MASQUERADE

iptables -t nat -A POSTROUTING -s 10.9.0.0/16 -j SNAT --to-source $IP

iptables -t nat -A POSTROUTING -j MASQUERADE

iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT

iptables -t nat -A PREROUTING -p tcp -m tcp --dport 440 -j DNAT --to-destination $IP:$vpnport

iptables -t nat -A PREROUTING -p tcp -m tcp --dport 1194 -j DNAT --to-destination $IP:$vpnport

iptables -t nat -A PREROUTING -p tcp -m tcp --dport 3389 -j DNAT --to-destination $IP:$vpnport

iptables -t nat -A PREROUTING -p udp -m udp --dport 67 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 68 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 69 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 136 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 137 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 138 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 139 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 636 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 1194 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 3389 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 5353 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -p udp -m udp --dport 6868 -j DNAT --to-destination $IP:53

iptables -t nat -A PREROUTING -d 10.8.0.1/16 -p udp -m udp --dport 53 -j DNAT --to-destination 10.9.0.1:35

iptables -t nat -A PREROUTING -d 10.9.0.1/16 -p udp -m udp --dport 53 -j DNAT --to-destination 10.8.0.1:35

service iptables save >/dev/null 2>&1

echo -e '鏈嶅姟鐘舵€侊細			  [\033[32m  OK  \033[0m]'

exit 0;" >/bin/fhq

chmod 777 /bin/fhq

echo

clear

echo "姝ｅ湪瀹夎HTTP杞彂妯″紡..."

cd /etc/openvpn

curl -O ${http}${host}${vpnfile}${mp}

chmod 0777 ${mp} >/dev/null 2>&1

echo

return 1

}

function installlamp() {

clear

echo "姝ｅ湪閮ㄧ讲浜戝厤娴佹帶鈩㈡瀬閫烲AMP鎼缓鑴氭湰..."

mkdir -p /home/wwwroot/default >/dev/null 2>&1

cd /root

wget ${http}${host}${vpnfile}res.zip >/dev/null 2>&1

unzip -o res.zip && chmod 0777 -R /root/res/

cp -rf /root/res/httpd.conf /etc/httpd/conf/httpd.conf

cp -rf /root/res/xyrml.service /lib/systemd/system/xyrml.service

sed -i 's/_listenport_/'${port}'/g' "/etc/httpd/conf/httpd.conf" >/dev/null 2>&1

echo "璁剧疆寮€鏈哄惎鍔�"

systemctl enable xyrml.service

echo

echo "#!/bin/bash

echo '姝ｅ湪閲嶅惎lamp鏈嶅姟...'

systemctl restart httpd.service

systemctl restart mariadb.service

systemctl restart crond.service

echo -e '鏈嶅姟鐘舵€侊細			  [\033[32m  OK  \033[0m]'

exit 0;" >/bin/lamp

chmod 777 /bin/lamp >/dev/null 2>&1

systemctl restart httpd.service

return 1

}

function webml() {

clear

echo "姝ｅ湪鍒濆鍖栦簯鍏嶆祦鎺р劉绋嬪簭鏁版嵁..."

echo "璇蜂笉瑕佽繘琛屼换浣曟搷浣�..."

cd /root

curl -O ${http}${host}${vpnfile}${webfile}

unzip -q ${webfile} >/dev/null 2>&1

sed -i 's/localhost/'$IP:$port'/g' ./xyr/web/install.sql >/dev/null 2>&1

cp /root/xyr/web/zdmc.sql /root/ >/dev/null 2>&1

cp /root/xyr/web/line.sql /root/ >/dev/null 2>&1

clear

echo "姝ｅ湪鍒涘缓鏁版嵁搴撹〃..."

create_db_sql="create database IF NOT EXISTS mydata"

mysql -hlocalhost -P3306 -uroot -p$sqlpass -e "${create_db_sql}"

echo

echo "鍒涘缓瀹屾垚锛�"

echo

mysql -hlocalhost -P3306 -uroot -p$sqlpass --default-character-set=utf8<<EOF

GRANT ALL PRIVILEGES ON *.* TO 'root'@'%'IDENTIFIED BY '${sqlpass}' WITH GRANT OPTION;

flush privileges;

use mydata;

source /root/xyr/web/install.sql;

EOF

echo "璁剧疆鏁版嵁搴撳畬鎴�"

mv -f ./xyr/sh/login.sh /etc/openvpn/ >/dev/null 2>&1

mv -f ./xyr/sh/disconnect.sh /etc/openvpn/ >/dev/null 2>&1

mv -f ./xyr/sh/connect.sh /etc/openvpn/ >/dev/null 2>&1

mv -f ./xyr/sh/xiaoyangren.net /etc/openvpn/ >/dev/null 2>&1

mv -f ./xyr/sh/crontab /etc/ >/dev/null 2>&1

chmod 0777 -R /etc/openvpn/

mv -f ./xyr/sh/xyr_hosts /home/ >/dev/null 2>&1

sed -i 's/xyrsql/'$sqlpass'/g' ./xyr/web/config.php >/dev/null 2>&1

mv -f ./xyr/web/* /home/wwwroot/default/ >/dev/null 2>&1

cd /home/wwwroot/default/

echo "echo -e '鍏抽棴鏁版嵁搴撹闂潈闄�		  [\033[32m  OK  \033[0m]'

chmod -R 644 /home/wwwroot/default/phpmyadmin && charrt +i /home/wwwroot/default/phpmyadmin

exit 0;

" >/bin/locksql

chmod 0755 /bin/locksql

echo "echo -e '寮€鍚暟鎹簱璁块棶鏉冮檺		  [\033[32m  OK  \033[0m]'

charrt -i /home/wwwroot/default/phpmyadmin && chmod -R 777 /home/wwwroot/default/phpmyadmin

exit 0;

" >/bin/onsql

chmod 0755 /bin/onsql

chmod 0755 /bin/locksql

echo "echo -e '閿佸畾娴佹帶鐩綍		  [\033[32m  OK  \033[0m]'

chattr +i /home/wwwroot/default/ && chattr -i /home/wwwroot/default/res/ && chattr -i /home/wwwroot/default/udp/ && chattr +i /home/wwwroot/default/user/ && chattr +i /home/wwwroot/default/config.php && chattr +i /home/wwwroot/default/admin/ && chattr +i /home/wwwroot/default/api.inc.php && chattr +i /home/wwwroot/default/daili/ && chattr +i /home/wwwroot/default/down/ && chattr +i /home/wwwroot/default/pay/ && chattr +i /home/wwwroot/default/web/ && chattr +i /home/wwwroot/default/360safe/ && chattr +i /home/wwwroot/default/app_api/ >/dev/null 2>&1

exit 0;

" >/bin/lockdir

chmod 0755 /bin/lockdir

echo "echo -e '瑙ｉ攣娴佹帶鐩綍		  [\033[32m  OK  \033[0m]'

chattr -i /home/wwwroot/default/ && chattr -i /home/wwwroot/default/user/ && chattr -i /home/wwwroot/default/config.php && chattr -i /home/wwwroot/default/admin/ && chattr -i /home/wwwroot/default/api.inc.php && chattr -i /home/wwwroot/default/daili/ && chattr -i /home/wwwroot/default/down/ && chattr -i /home/wwwroot/default/pay/ && chattr -i /home/wwwroot/default/web/ && chattr -i /home/wwwroot/default/360safe/ && chattr -i /home/wwwroot/default/assets/

exit 0;

" >/bin/ondir

chmod 0755 /bin/ondir

echo "echo -e '鐩戞帶鍚姩瀹屾垚		  [\033[32m  OK  \033[0m]'

/home/wwwroot/default/res/jiankong >>/home/wwwlog/jiankong.log 2>&1 & /home/wwwroot/default/udp/jiankong >>/home/wwwlog/jiankong-udp.log 2>&1 &

exit 0;

" >/bin/opmt

chmod 0755 /bin/opmt

echo "echo -e '閿佸畾娴侀噺鍗＋鐩綍		  [\033[32m  OK  \033[0m]'

chmod -R 0555 /home/wwwroot/default/app_api/

chmod -R 0777 /home/wwwroot/default/app_api/data/content.txt && chmod -R 0777 /home/wwwroot/default/app_api/data/default.txt && chmod -R 0777 /home/wwwroot/default/app_api/data/max_limit.txt && chmod -R 0777 /home/wwwroot/default/app_api/data/reg_type.txt

chattr +i /home/wwwroot/default/app_api/

exit 0;

" >/bin/llws

chmod 0755 /bin/llws

echo "echo -e '瑙ｉ攣娴侀噺鍗＋鐩綍		  [\033[32m  OK  \033[0m]'

chattr -i /home/wwwroot/default/app_api/

chmod -R 0777 /home/wwwroot/default/app_api/

exit 0;

" >/bin/onllws

chmod 0755 /bin/onllws

rm -rf /root/xyr* >/dev/null 2>&1

rm -rf /root/res* >/dev/null 2>&1

yum install -y crontabs >/dev/null 2>&1

mkdir -p /var/spool/cron/ >/dev/null 2>&1

echo

echo "姝ｅ湪瀹夎瀹炴椂鐩戞帶绋嬪簭锛�"

echo "* * * * * curl --silent --compressed http://${IP}:${port}/cron.php">>/var/spool/cron/root

systemctl restart crond.service

systemctl enable crond.service

chmod 755 /home/wwwroot/default/res >/dev/null 2>&1

cd /home/wwwroot/default/res/

curl -O ${http}${host}${vpnfile}${jiankong_tcp} >/dev/null 2>&1

unzip ${jiankong_tcp} >/dev/null 2>&1

rm -rf ${jiankong_tcp}

chmod 777 jiankong

chmod 777 sha

chmod 755 /home/wwwroot/default/udp >/dev/null 2>&1

cd /home/wwwroot/default/udp

curl -O ${http}${host}${vpnfile}${jiankong_udp} >/dev/null 2>&1

unzip ${jiankong_udp} >/dev/null 2>&1

rm -rf ${jiankong_udp}

chmod 777 jiankong

chmod 777 sha

echo "localhost=localhost

port=3306

root=root

mima=$sqlpass

databases=mydata

shujuku=mydata">>/etc/openvpn/sqlmima

chmod 777 /etc/openvpn/sqlmima

echo "db_pass="$sqlpass"

db_name=mydata">>/etc/openvpn/xyr

chmod 777 /etc/openvpn/xyr

/home/wwwroot/default/res/jiankong >>/home/wwwlog/jiankong.log 2>&1 &

/home/wwwroot/default/udp/jiankong >>/home/wwwlog/jiankong-udp.log 2>&1 &

echo "/home/wwwroot/default/res/jiankong >>/home/wwwlog/jiankong.log 2>&1 &">>/etc/rc.local

echo "/home/wwwroot/default/udp/jiankong >>/home/wwwlog/jiankong-udp.log 2>&1 &">>/etc/rc.local

echo "fhq >/dev/null 2>&1">>/etc/rc.local

chmod +x /etc/rc.local

vpn >/dev/null 2>&1

echo

echo "Web娴侀噺鎺у埗绋嬪簭瀹夎瀹屾垚..."

return 1

}

function liuliangweishi() {

cd ${web_path}

wget ${http}${host}${vpnfile}app_api.zip && unzip -o app_api.zip >/dev/null 2>&1

rm app_api.zip

cd ${web_path}/app_api

sed -i 's/123456/'$sqlpass'/g' ${web_path}app_api/config.php >/dev/null 2>&1

sed -i 's/RANDOM/'mydata'/g' ${web_path}app_api/config.php >/dev/null 2>&1

mysql -hlocalhost -P3306 -uroot -p$sqlpass --default-character-set=utf8<<EOF

GRANT ALL PRIVILEGES ON *.* TO 'root'@'%'IDENTIFIED BY '${sqlpass}' WITH GRANT OPTION;

flush privileges;

use mydata;

source ${web_path}app_api/install/data/ov.sql;

EOF

echo "瀹夎娴侀噺鐩戞帶..."

wget -O disconnect.sh ${http}${host}${vpnfile}disconnected.sh

sed -i 's/192.168.1.1:8888/'${IP}:${port}'/g' "disconnect.sh" >/dev/null 2>&1

if test -f /etc/openvpn/disconnect.sh;then

	chmod 0777 -R /etc/openvpn/

	cp -rf /etc/openvpn/disconnect.sh /etc/openvpn/disconnect.sh.bak

	cp -rf disconnect.sh /etc/openvpn/disconnect.sh

	chmod 0777 /etc/openvpn/disconnect.sh

fi

chmod 0777 -R /home

cd /home

echo  "寮€濮嬪埗浣淎PP"

echo "姝ｅ湪鍔犺浇鍩虹鐜(杈冩參 鑰愬績绛夊緟)...."

yum install -y java

echo "涓嬭浇APK鍖�"

wget -O android.apk ${http}${host}${vpnfile}v5.apk

echo "娓呯悊鏃х殑鐩綍"

rm -rf android

echo "鍒嗘瀽APK"

wget -O apktool.jar ${http}${host}${vpnfile}apktool.jar&&java -jar apktool.jar d android.apk

echo "鎵归噺鏇挎崲"

chmod 0777 -R /home/android

sed -i 's/demo.dingd.cn:80/'${IP}:${port}'/g' `grep demo.dingd.cn:80 -rl /home/android/smali/net/openvpn/openvpn/` >/dev/null 2>&1

sed -i 's/鍙挌娴侀噺鍗＋/'${app_name}'/g' "/home/android/res/values/strings.xml" >/dev/null 2>&1

echo "鎵撳寘"

java -jar apktool.jar b android

if test -f /home/android/dist/android.apk;then

echo "APK鐢熸垚瀹屾瘯"

wget -O autosign.zip ${http}${host}${vpnfile}autosign.zip && unzip -o autosign.zip

rm -rf ${web_path}/app_api/dingd.apk

cd autosign

echo "姝ｅ湪绛惧悕APK...."

cp -rf /home/android/dist/android.apk /home/unsign.apk

java -jar signapk.jar testkey.x509.pem testkey.pk8 /home/unsign.apk /home/sign.apk

cp -rf /home/sign.apk  /home/xianlu/xyrml.apk

echo "姝ｅ湪娓呯悊涓存椂鏂囦欢...."	

rm -rf /home/dingd.apk /home/sign.apk /home/unsign.apk /home/android.apk /home/android /home/autosign.zip /home/apktool.jar /home/setup.bash /home/autosign

llwssfyaz="宸�"

dadas="1"

fi

return 1

}

function ovpn() {

echo

echo "寮€濮嬬敓鎴愰厤缃枃浠�..."

mkdir /home/xianlu

cd /home/xianlu

wget ${http}${host}${vpnfile}line.zip >/dev/null 2>&1

unzip line.zip >/dev/null 2>&1

sed -i "s/localxyrml/$IP/g;s/mpxyrml/$mpport/g;s/sqxyrml/$sqport/g;s/portxyrml/$vpnport/g" `grep 'localxyrml' -rl .`

echo

echo "閰嶇疆鏂囦欢鍒朵綔瀹屾瘯"

echo

cd /root

sed -i 's/浜戞祦閲�/'$webname'/g' zdmc.sql >/dev/null 2>&1

sed -i 's/ov/'mydata'/g' zdmc.sql >/dev/null 2>&1

sed -i 's/666/'$qie'/g' zdmc.sql >/dev/null 2>&1

sed -i "s/xyr-dl/`echo $RANDOM`/g" zdmc.sql >/dev/null 2>&1

sed -i 's/123456789/'$adminuser'/g' zdmc.sql >/dev/null 2>&1

sed -i 's/987654321/'$adminpass'/g' zdmc.sql >/dev/null 2>&1

mysql -hlocalhost -P3306 -uroot -p$sqlpass --default-character-set=utf8<<EOF

GRANT ALL PRIVILEGES ON *.* TO 'root'@'%'IDENTIFIED BY '${sqlpass}' WITH GRANT OPTION;

flush privileges;

use mydata;

source zdmc.sql;

source line.sql;

EOF

rm -rf *.sql

rm -rf ${web_path}*.sql

if [[ $llwsapp == "y" ]] || [[ $llwsapp == "Y" ]] || [[ $llwsapp == "" ]];then

liuliangweishi

fi

return 1

}

function shujukubeifen() {

wget -P /home ${http}${host}${vpnfile}backupsql.sh >/dev/null 2>&1

mkdir -p /root/backup/mysql >/dev/null 2>&1

chmod 755 /home/backupsql.sh >/dev/null 2>&1

}

function shuchuliuliangweishianzhuangxinxi() {

echo "------------------------------------------------------------

APP涓嬭浇锛歨ttp://$IP:$port/xyrml.apk

------------------------------------------------------------">>/root/info.txt

}

function webmlpass() {

cd /home

shujukubeifen

bash backupsql.sh

echo '娆㈣繋浣跨敤浜戝厤娴佹帶鈩㈢郴缁�

' >>/root/info.txt

echo

if [[ $llwsapp == "y" ]] || [[ $llwsapp == "Y" ]] || [[ $llwsapp == "" ]];then

shuchuliuliangweishianzhuangxinxi

fi

echo

echo "鏁版嵁搴撴瘡1鍒嗛挓鑷姩澶囦唤锛屽浠芥暟鎹簱鏂囦欢鍦�/root/backup/mysql/

------------------------------------------------------------

鏁版嵁搴撳悗鍙帮細http://${IP}:${port}/phpmyadmin

------------------------------------------------------------

鏁版嵁搴撶敤鎴峰悕锛歳oot 瀵嗙爜锛�${sqlpass} 鏁版嵁搴撳悕锛歮ydata

------------------------------------------------------------

鍚庡彴绠＄悊绯荤粺锛�${IP}:${port}/admin

------------------------------------------------------------

鍚庡彴绠＄悊鍛樼敤鎴峰悕锛�$adminuser 绠＄悊瀵嗙爜锛�$adminzanshi

------------------------------------------------------------

鍓嶅彴/鐢ㄦ埛涓績锛岀敤鎴锋煡娴侀噺鐨勭綉鍧€锛歨ttp://${IP}:${port}/user

------------------------------------------------------------

浠ｇ悊涓績锛歨ttp://${IP}:${port}/daili

------------------------------------------------------------

娴佹帶缃戦〉绋嬪簭鏂囦欢鐩綍涓�:/home/wwwroot/default/

------------------------------------------------------------

鑱氬姏缃戠粶娴佹帶瀹樻柟浜ゆ祦缇わ細756823984	浣曚互娼嘠Q锛�1744744000 

------------------------------------------------------------

璇风櫥褰曟祦鎺х鐞嗗悗鍙�->鈥滄縺娲荤嚎璺€� 婵€娲绘渶鏂版祦鎺ц嚜甯︾嚎璺�

------------------------------------------------------------">>/root/info.txt

return 1

}

function pkgovpn() {

clear

echo "姝ｅ湪鎵撳寘閰嶇疆鏂囦欢锛岃绋嶇瓑..."

cp ${web_path}openvpn.apk /home/xianlu >/dev/null 2>&1

cd /home/xianlu

zip ${uploadfile} ./{yd-05.17-闄曡タ绉诲姩.ovpn,yd-05.17-骞夸笢涓滆帪1.ovpn,yd-05.17-骞夸笢涓滆帪2.ovpn,yd-05.17-骞夸笢鑼傚悕.ovpn,yd-05.17-骞夸笢婀涙睙.ovpn,yd-05.17-骞夸笢绉诲姩.ovpn,yd-05.17-璐靛窞姣曡妭.ovpn,yd-05.17-璐靛窞绉诲姩.ovpn,yd-05.17-婀栧崡绉诲姩1.ovpn,yd-05.17-婀栧崡姘稿窞.ovpn,yd-05.17-姹熻嫃鑻忓窞.ovpn,yd-05.17-婀栧寳绉诲姩1.ovpn,yd-05.17-灞变笢绉诲姩1.ovpn,yd-05.17-灞辫タ绉诲姩1.ovpn,yd-05.17-鍥涘窛杈惧窞.ovpn,yd-05.17-瀹夊窘鍚堣偉.ovpn,yd-05.17-绉诲姩鍜崱.ovpn,yd-05.17-浜戝崡绉诲姩.ovpn,yd-05.17-榛戦緳姹熺Щ鍔�.ovpn,dx-05.17-鍥涘窛鐢典俊.ovpn,lt-05.17-骞夸笢鑱旈€�.ovpn,lt-05.17-婀栧寳鑱旈€�.ovpn,lt-05.17-閲嶅簡鑱旈€�.ovpn,yd-05.01-鍚夋灄闀挎槬1.ovpn,yd-05.01-鍖椾含绉诲姩1.ovpn,yd-05.01-婀栧寳绉诲姩1.ovpn,yd-05.01-婀栧寳绉诲姩2.ovpn,yd-05.01-婀栧寳绉诲姩3.ovpn,yd-05.01-婀栧寳榛勭煶1.ovpn,yd-05.01-婀栧寳鍗佸牥1.ovpn,yd-05.01-婀栧寳瀛濇劅1.ovpn,yd-05.01-杈藉畞绉诲姩1.ovpn,yd-05.01-杈藉畞绉诲姩2.ovpn,yd-05.01-鍏ㄥ浗绉诲姩1.ovpn,yd-05.01-鍥涘窛鎴愰兘1.ovpn,yd-05.01-骞夸笢涓滆帪1.ovpn,yd-05.01-骞胯タ宕囧乏1.ovpn,yd-05.01-骞胯タ澶嶆椿1.ovpn,yd-05.01-骞胯タ璐哄窞1.ovpn,yd-05.01-鍗楀畞璐哄窞1.ovpn,yd-05.01-瀹夊窘绉诲姩1.ovpn,yd-05.01-璐靛窞绉诲姩1.ovpn,yd-05.01-姹熻嫃绉诲姩1.ovpn,yd-05.01-姹熻タ璧ｅ窞1.ovpn,yd-05.01-浜戝崡绉诲姩1.ovpn,yd-05.01-灞变笢绉诲姩1.ovpn,yd-05.01-婀栧崡绉诲姩1.ovpn,yd-05.01-婀栧崡闀挎矙1.ovpn,yd-05.01-骞胯タ闃插煄娓�1.ovpn,yd-05.01-婀栧崡閮村窞宀抽槼1.ovpn,yd-05.01-鍏ㄥ浗wap妯″紡.ovpn,yd-05.01-灞变笢娴庡崡.ovpn,yd-05.01-灞变笢涓存矀.ovpn,yd-05.01-灞变笢涓存矀2.ovpn,yd-05.01-灞辫タ鍏ㄧ渷.ovpn,yd-05.01-闄曡タ瀹濋浮.ovpn,yd-05.01-涓婃捣绉诲姩.ovpn,yd-05.01-鍥涘窛涓嶉檺閫�.ovpn,yd-05.01-鍥涘窛涓嶉檺閫�2.ovpn,yd-05.01-鍥涘窛绉诲姩.ovpn,yd-05.01-鍥涘窛鎴愰兘2.ovpn,yd-05.01-鍥涘窛杈惧窞.ovpn,yd-05.01-姝︽眽绉诲姩443.ovpn,yd-05.01-鏂板挭鍜曠Щ鍔�.ovpn,yd-05.01-骞夸笢鍏ㄦ柊绉诲姩.ovpn,yd-05.01-骞胯タ澶嶆椿2.ovpn,yd-05.01-鐮磋В绉诲姩.ovpn,yd-05.01-绉诲姩浜戝崡erkuailife.ovpn,yd-05.01-绉诲姩浜戝崡138.ovpn,yd-05.01-绉诲姩浜戝崡IP.ovpn,dx-05.01-鍚夋灄鐢典俊.ovpn,dx-05.01-灞变笢鐢典俊.ovpn,dx-05.01-闄曡タ鐢典俊.ovpn,dx-05.01-鍥涘窛鐢典俊.ovpn,dx-05.01-澶╃考瑙嗚.ovpn,lt-05.01-闄曡タ鑱旈€�.ovpn,lt-05.01-鍏ㄥ浗澶х帇鍗�.ovpn,lt-05.01-骞夸笢鑱旈€�.ovpn,lt-05.01-骞胯タ鑱旈€�.ovpn,lt-05.01-婀栧崡鑱旈€�.ovpn,lt-05.01-鑱旈€歂ET.ovpn,lt-05.01-鍥涘窛蹇呭厤.ovpn,lt-05.01-鍥涘窛鑱旈€�.ovpn,lt-05.01-鍥涘窛鑱旈€�2.ovpn,lt-05.01-灞变笢鑱旈€�.ovpn,yd-04.14-浜戝崡鏄€�.ovpn,yd-04.14-鍖椾含绉诲姩.ovpn,yd-04.14-骞夸笢绉诲姩.ovpn,yd-04.14-娌冲崡娲涢槼.ovpn,yd-04.14-姹熻嫃绉诲姩.ovpn,yd-04.14-姹熻タ绉诲姩.ovpn,yd-04.14-骞夸笢鑼傚悕.ovpn,yd-04.14-闄曡タ绉诲姩.ovpn,yd-04.14-涓婃捣绉诲姩.ovpn,yd-04.14-婀栧崡琛￠槼.ovpn,yd-04.14-鐢樿們绉诲姩.ovpn,yd-04.14-婀栧寳瑗勯槼鍗佸牥.ovpn,yd-04.14-鍥涘窛宸翠腑鏄屽钩.ovpn,yd-04.14-鍥涘窛骞垮厓鎴愰兘.ovpn,yd-04.14-瀹夊窘铓屽煚瀹垮窞.ovpn,yd-04.14-浜戝崡绉诲姩鐞嗚鍏ㄥ厤.ovpn,lt-04.14-鍥涘窛鑱旈€�.ovpn,lt-04.14-鍏ㄥ浗鑱旈€�.ovpn,dx-04.14-鍥涘窛鐢典俊.ovpn,dx-04.14-鐢樿們鐢典俊.ovpn,dx-04.14-鍏ㄥ浗鐢典俊.ovpn,yd-04.08-婀栧崡濞勫簳.ovpn,yd-04.08-婀栧崡闀挎矙.ovpn,yd-04.08-婀栧崡姘稿窞.ovpn,yd-04.08-灞辫タ绉诲姩.ovpn,yd-04.08-鍥涘窛绉诲姩.ovpn,d-04.08-鍥涘窛绉诲姩2.ovpn,yd-04.08-灞辫タ杩愬煄.ovpn,yd-04.08-灞辫タ杩愬煄2.ovpn,yd-04.08-灞辫タ涓存本杩愬煄鏅嬪煄.ovpn,yd-04.08-灞辫タ澶у悓.ovpn,yd-04.08-灞变笢鑱婂煄.ovpn,yd-04.08-涓存本杩愬煄闀挎不.ovpn,yd-04.08-婀栧寳姝︽眽.ovpn,yd-04.08-娌冲寳鍞愬北.ovpn,yd-04.08-骞垮窞绉诲姩.ovpn,yd-04.08-骞胯タ宕囧乏.ovpn,yd-04.08-骞胯タ鍖楁捣.ovpn,yd-04.08-骞夸笢浣涘北.ovpn,yd-04.08-绂忓缓绉诲姩涓嶉檺閫�.ovpn,lt-04.08-鍏ㄥ浗鑱旈€氬ぇ鐜嬪崱鍏ㄥ浗鍏�.ovpn,lt-04.08-骞胯タ鑱旈€�.ovpn,dx-04.08-姹熻嫃鑻忓窞鐢典俊.ovpn,dx-04.08-鍗楀畞鐢典俊.ovpn,dx-04.08-骞胯タ鍖楁捣鐢典俊.ovpn,yd-03.26-gxbf.ovpn,lt-03.26-qgdwk.ovpn,lt-03.26-sd.ovpn,lt-03.26-cq.ovpn,yd-03.26-sc1.ovpn,yd-03.26-sc2.ovpn,yd-03.26-gxnn.ovpn,yd-03.26-sd1.ovpn,yd-03.26-sd2.ovpn,dx-03.26-hbdx.ovpn,yd-03.26-hn.ovpn,yd-03.26-dg.ovpn,yd-03.26-sx.ovpn,yd-03.26-gz.ovp.ovpn,yd-03.26-gdsz1.ovpn,yd-03.26-gdsz2.ovpn,yd-03.26-fjxm.ovpn,dx-03.26-sxdx.ovpn,lt-03.26-gx.ovpn,lt-03.26-qg.ovpn,xyrml-yd-old.ovpn,xyrml-yd-udp138.ovpn,xyrml-yd-udp53.ovpn,xyrml-yd-udp137.ovpn,xyrml-yd-138.ovpn,xyrml-yd-138鈶�.ovpn,xyrml-yd-mg138.ovpn,xyrml-yd-zj鈶�.ovpn,xyrml-lt-2.ovpn,xyrml-yd-137.ovpn,xyrml-yd-old-366.ovpn,xyrml-yd-old-351.ovpn,xyrml-yd-fj.ovpn,xyrml-yd-gs.ovpn,xyrml-yd-gs2.ovpn,xyrml-yd-gs3.ovpn,xyrml-yd-gs4.ovpn,xyrml-yd-gd2.ovpn,xyrml-yd-gdsz2.ovpn,xyrml-yd-gdsz1.ovpn,xyrml-yd-gd1.ovpn,xyrml-yd-gd4.ovpn,xyrml-yd-gd5.ovpn,xyrml-yd-gd6.ovpn,xyrml-yd-gd7.ovpn,xyrml-yd-gd3.ovpn,xyrml-yd-gx.ovpn,xyrml-yd-hebei2.ovpn,xyrml-yd-hebei.ovpn,xyrml-yd-sd.ovpn,xyrml-yd-sd2.ovpn,xyrml-yd-sxi.ovpn,xyrml-yd-sx.ovpn,xyrml-yd-sx1.ovpn,xyrml-yd-sx3.ovpn,xyrml-yd-sxjx.ovpn,xyrml-yd-jx2.ovpn,xyrml-yd-jx.ovpn,xyrml-yd-sc鈶�.ovpn,xyrml-yd-sc1.ovpn,xyrml-yd-sc2.ovpn,xyrml-yd-sc2.ovpn,xyrml-yd-maom.ovpn,xyrml-yd-zj鈶�.ovpn,xyrml-yd-zj鈶�.ovpn,xyrml-yd-ln.ovpn,xyrml-yd-hb.ovpn,xyrml-yd-hn.ovpn,xyrml-lt-dwk2.ovpn,xyrml-lt-tj.ovpn,xyrml-dx-sjl.ovpn,xyrml-yd-qgzq.ovpn,xyrml-lt-hb.ovpn,xyrml-lt-zj.ovpn,xyrml-lt-bj.ovpn,xyrml-lt-uac2.ovpn,xyrml-lt-uac3.ovpn,xyrml-dx-cq.ovpn,xyrml-dx-qg1.ovpn,xyrml-yd-nx.ovpn,xyrml-yd-hun1.ovpn,xyrml-yd-gz.ovpn,xyrml-yd-136.ovpn,xyrml-yd-139.ovpn,xyrml-yd-mm.ovpn,xyrml-yd-js.ovpn,xyrml-yd-ah.ovpn,xyrml-yd-neimenggu.ovpn,xyrml-yd-migu1.ovpn,xyrml-yd-migu.ovpn,xyrml-yd-migu2.ovpn,xyrml-yd-migu3.ovpn,xyrml-yd-migu2-137.ovpn,xyrml-yd-migu-137.ovpn,xyrml-yd-qg7.ovpn,xyrml-yd-qg8.ovpn,xyrml-yd-qgA.ovpn,xyrml-yd-qg9.ovpn,xyrml-lt-uac.ovpn,xyrml-lt-53.ovpn,xyrml-lt-1.ovpn,xyrml-lt-qglt.ovpn,xyrml-lt-gd.ovpn,xyrml-lt-3.ovpn,xyrml-lt-4.ovpn,xyrml-lt-5.ovpn,xyrml-lt-qg1.ovpn,xyrml-lt-wap.ovpn,xyrml-lt-dwk.ovpn,xyrml-dx-1.ovpn,xyrml-dx-gd.ovpn,xyrml-dx-llqg.ovpn,xyrml-dx-yinyue.ovpn,2017-xyrml-yd-sh.ovpn,2017-xyrml-yd-qg1.ovpn,2017-xyrml-yd-qg2.ovpn,2017-xyrml-yd-sc.ovpn,2017-xyrml-yd-gd.ovpn,2017-xyrml-yd-cq.ovpn,2017-xyrml-yd-zj.ovpn,2017-xyrml-yd-yn.ovpn,2017-xyrml-yd-sz.ovpn,2017-xyrml-yd-st.ovpn,2017-xyrml-yd-sx.ovpn,2017-xyrml-yd-sd.ovpn,2017-xyrml-yd-ln.ovpn,2017-xyrml-yd-jl.ovpn,2017-xyrml-yd-hunan.ovpn,2017-xyrml-yd-henan.ovpn,2017-xyrml-yd-hebei.ovpn,2017-xyrml-yd-guangzhou.ovpn,2017-xyrml-yd-guangxi.ovpn,2017-xyrml-yd-jiangxi.ovpn,2017-xyrml-yd-gansu.ovpn,2017-xyrml-yd-maom.ovpn,2017-xyrml-yd-guiz.ovpn,2017-xyrml-yd-ah.ovpn,2017-xyrml-yd-bj.ovpn,2017-xyrml-yd-fj.ovpn,2017-xyrml-yd-hubei.ovpn,2017-xyrml-yd-ln2.ovpn,2017-xyrml-yd-sd2.ovpn,2017-xyrml-yd-sx2.ovpn,2017-xyrml-yd-yn2.ovpn,2017-xyrml-yd-cq2.ovpn,2017-xyrml-yd-hebei2.ovpn,2017-xyrml-yd-hunan2.ovpn,2017-xyrml-lt-qg1.ovpn,2017-xyrml-lt-qg2.ovpn,2017-xyrml-lt-qg3.ovpn,2017-xyrml-lt-gd.ovpn,2017-xyrml-lt-uac1.ovpn,2017-xyrml-lt-uac2.ovpn,2017-xyrml-lt-ts.ovpn,2017-xyrml-new-dwk.ovpn,2017-xyrml-dx-ak.ovpn,2017-xyrml-dx-gx.ovpn,2017-xyrml-dx-aw.ovpn,2017-xyrml-dx-qg.ovpn,2017-xyrml-lt-53.ovpn,2017-xyrml-yd-henan2.ovpn,03-xyrml-yd-gdzj.ovpn,03-xyrml-yd-sx.ovpn,03-xyrml-yd-hb.ovpn,03-xyrml-yd-cq.ovpn,03-xyrml-lt-cq.ovpn,03-xyrml-lt-zj.ovpn,03-xyrml-yd-zj.ovpn,03-xyrml-dx-zj.ovpn,03-xyrml-yd-yn1.ovpn,03-xyrml-yd-yn2.ovpn,03-xyrml-dx-xdx.ovpn,03-xyrml-yd-xj1.ovpn,03-xyrml-yd-xj2.ovpn,03-xyrml-yd-xz.ovpn,03-xyrml-lt-wz.ovpn,03-xyrml-yd-tj.ovpn,03-xyrml-yd-sc.ovpn,03-xyrml-dx-sc.ovpn,03-xyrml-yd-sh1.ovpn,03-xyrml-yd-sh2.ovpn,03-xyrml-yd-zq.ovpn,xyrml-yd-3.11-yn.ovpn,xyrml-yd-3.11-st.ovpn,xyrml-yd-3.11-nn.ovpn,xyrml-yd-3.11-qg1.ovpn,xyrml-yd-3.11-jl.ovpn,xyrml-yd-3.11-qg2.ovpn,xyrml-yd-3.11-hb.ovpn,xyrml-yd-3.11-sz.ovpn,xyrml-yd-3.11-cq.ovpn,xyrml-yd-3.11-qg3.ovpn,xyrml-yd-3.11-ah.ovpn,xyrml-yd-3.11-qg4.ovpn,xyrml-yd-3.11-qg5.ovpn,xyrml-yd-3.11-nx.ovpn,xyrml-yd-3.11-qg6.ovpn,xyrml-yd-3.11-lf.ovpn,xyrml-yd-3.11-qg7.ovpn,xyrml-yd-3.11-qg8.ovpn,xyrml-yd-3.11-fj.ovpn,xyrml-yd-3.11-qg9.ovpn,xyrml-yd-3.11-teshu-migu.ovpn,xyrml.apk,openvpn.apk,ca.crt,ta.key} >/dev/null 2>&1

cp /home/xianlu/xyrml.apk ${web_path} >/dev/null 2>&1

cp /home/xianlu/ca.crt ${web_path} >/dev/null 2>&1

cp /home/xianlu/ta.key ${web_path} >/dev/null 2>&1

cd /home

echo

echo "姝ｅ湪鍔犺浇鎮ㄧ殑閰嶇疆淇℃伅..."

echo

cat /root/info.txt

echo

echo "鎮ㄧ殑绾胯矾/璇佷功/key/浜戠APP/绛夐噸瑕佸唴瀹逛笅杞界綉鍧€濡備笅锛�"

cp -rf /home/xianlu/${uploadfile} ${web_path}${uploadfile}

rm -rf /home/xianlu

echo

echo "http://${IP}:${port}/${uploadfile}"

echo

echo "鎮ㄧ殑IP鏄細$IP 锛堝鏋滀笌鎮ㄥ疄闄匢P涓嶇鍚堟垨绌虹櫧锛岃鑷淇敼.ovpn閰嶇疆锛�"

chmod 0777 -R /home/

return 1

}

function main() {

shellhead

clear

echo -e '\033[33m================鈽嗏槅========================================================\033[0m'

echo -e '\033[33m                浜戝厤娴佹帶鈩�-Web娴佹帶绯荤粺 浜戝厤鏈嶅姟鍣ㄤ竴閿惌寤篭033[0m'

echo -e '\033[33m                        Powered by www.juliwangluo.cn 2019\033[0m'

echo -e '\033[33m                        All Rights Reserved\033[0m'

echo -e '\033[33m                鑱氬姏娴佹帶浜ゆ祦缇わ細756823984	浣曚互娼嘠Q锛�1744744000  娆㈣繋浣犵殑鍔犲叆锛乗033[0m'

echo -e '\033[33m                鏈剼鏈凡閫氳繃闃块噷浜� 鑵捐浜� 楂橀槻鏈嶅姟鍣� 绛変竴绯诲垪鏈嶅姟鍣╘033[0m'

echo -e '\033[34m                瀹樻柟缃戝潃锛歨ttp://www.juliwangluo.cn/\033[0m'

echo -e '\033[33m================鈽嗏槅========================================================\033[0m'

echo

authentication

InputIPAddress

clear

echo -e '\033[33m================鈽嗏槅========================================================\033[0m'

echo -e '\033[33m                浜戝厤娴佹帶鈩�-Web娴佹帶绯荤粺 浜戝厤鏈嶅姟鍣ㄤ竴閿惌寤篭033[0m'

echo -e '\033[33m                娓╅Θ鎻愮ず锛歕033[0m'

echo -e '\033[33m                瀵嗛挜缁戝畾IP鍙湪鍚屼竴IP涓嬪弽澶嶄娇鐢紒\033[0m'

echo -e '\033[34m                    瀹樻柟缃戝潃锛歨ttp://www.juliwangluo.cn/\033[0m'

echo -e '\033[33m                鑱氬姏娴佹帶浜ゆ祦缇わ細756823984	浣曚互娼嘠Q锛�1744744000  娆㈣繋浣犵殑鍔犲叆锛乗033[0m'

echo -e '\033[33m================鈽嗏槅========================================================\033[0m'

echo

echo -e "\033[36m鎮ㄦ湇鍔″櫒IP鏄細$IP 濡傛灉涓嶆纭涓瀹夎骞惰仈绯荤鐞嗗憳锛乗033[0m"

echo

echo -e '\033[33m璇疯緭鍏ユ鐗堝瘑閽ュ紑鍚畨瑁呭悜瀵硷紙璐拱缃戝潃:\033[32m www.juliwangluo.cn \033[0m锛�'

echo

echo -e "\033[34m浣曚互娼囨彁绀猴細绉橀挜闅忎究杈撳叆锛乗033[0m"

echo  -n -e '\033[33m璇疯緭鍏ユ巿鏉冨瘑閽ワ細\033[0m'

read card

#curl "http://www.xiaoyangren.net/sq/status.php?url=$IP&km=$card&qq=$qie" >/dev/null 2>&1

echo

echo "姝ｅ湪楠岃瘉鎺堟潈..."

kcard=yes #鐮磋В鎺堟潈

#kcard=`curl -s http://www.xiaoyangren.net/sq/card.php?url=${IP}"&km="${card}"&qq="${qie}`;

if [[ "$kcard" == "no" ]] || [ "$kcard" == "" ]

then

echo -e '\033[33m==========================================================================\033[0m'

echo -e '\033[34m               鏈兘閫氳繃楠岃瘉 璇风‘璁ゆ偍鐨勫瘑閽ユ槸鍚︽纭紒\033[0m'

echo -e '\033[31m               娓╅Θ鎻愮ず锛歕033[0m'

echo -e '\033[33m               姝ｇ増瀵嗛挜10鍏�/1浠禱033[0m'

echo -e '\033[31m               瀵嗛挜缁戝畾IP鍙湪鍚屼竴IP涓嬪弽澶嶄娇鐢紒\033[0m'

echo -e '\033[33m               瀹樻柟缃戝潃锛歨ttp://www.juliwangluo.cn/\033[0m'

echo -e '\033[31m               鑱氬姏娴佹帶浜ゆ祦缇わ細756823984	浣曚互娼嘠Q锛�1744744000  娆㈣繋浣犵殑鍔犲叆锛乗033[0m'

echo -e '\033[33m==========================================================================\033[0m'

exit 0;

else

if [[ "$kcard" == "yes" ]]

then

echo

echo -e "鎺堟潈鐘舵€�  $IP  [\033[32m  鎺堟潈鎴愬姛  \033[0m]";

echo "鎺堟潈鐮佸凡鎴愬姛缁戝畾鎮ㄧ殑鏈嶅姟鍣↖P锛屾敮鎸佹案涔呮棤闄愪娇鐢紒";

echo "鍗冲皢寮€濮嬩笅涓€姝ュ畨瑁�..."

sleep 0.5

echo "璇烽€夋嫨瀹夎绫诲瀷锛�"

echo

echo "1 - 鍏ㄦ柊瀹夎(鍥炶溅榛樿) < 鏂拌+娴佹帶绯荤粺"

echo -e "        \033[31m鎻愮ず锛歕033[0m\033[35m鏀寔闃块噷浜戙€佽吘璁簯绛夋瑙勬湇鍔″晢 Centos7.x 64浣嶅叏鏂扮郴缁�. \033[0m"

echo -e "        \033[31m\033[0m\033[35m寮€鏀惧绔彛TCP-UDP鍏卞瓨 瀹炴椂鐩戞帶 绛�... \033[0m"

echo -e "        鑵捐浜戯細璇烽粯璁ゅ畨鍏ㄧ粍鏀鹃€氬叏閮ㄧ鍙�."

echo

echo "2 - 瀵规帴妯″紡 >> 瀹炵幇N鍙版湇鍔″櫒鍏辩敤璐﹀彿"

echo -e "        \033[31m鎻愮ず锛歕033[0m\033[35m \033[0m"

echo -e "        涓€閿厤缃叡鐢ㄦ暟鎹簱骞剁粺涓€璇佷功锛岄渶闆嗙兢璐熻浇锛岀敤鍩熷悕杩涜璐熻浇鍧囪　鍗冲彲"

echo -e "        璇风敤闇€瑕佸鎺ヤ富鏈嶅姟鍣ㄧ殑瀛愭湇鍔″櫒鎵ц姝ら€夐」瀹屾垚瀵规帴"

echo

echo -n -e "璇疯緭鍏ュ搴旂殑閫夐」:"

read installslect

if [[ "$installslect" == "2" ]]

then

clear

echo "-------------------------------------------"

echo "璐熻浇鍧囪　蹇呯湅璇存槑锛�"

echo "涓ゅ彴鏈嶅姟鍣ㄥ繀椤婚兘宸插畨瑁呬簯鍏嶆祦鎺р劉鑴氭湰绋嬪簭"

echo "骞惰兘姝ｅ父杩愯鍜岃繛鎺ユ湇鍔″櫒"

echo "涓旀暟鎹簱璐﹀彿-瀵嗙爜-绔彛-绠＄悊鍛樿处鍙�-瀵嗙爜 闇€淇濇寔涓€鑷达紒"

echo "-------------------------------------------"

echo

echo "璇锋彁渚涗富鏈嶅姟鍣ㄥ拰鍓満淇℃伅:"

echo -e "      \033[31m娉ㄦ剰锛歕033[0m\033[35m璇峰瀹炲～鍐欎俊鎭紝鍚﹀垯鍚庢灉鑷礋锛�. \033[0m"

echo -e "      璇锋牳瀵逛粩缁嗘棤閿欏悗鍐嶈繘琛屽洖杞�."

echo

echo -n -e "璇疯緭鍏ヤ富鏈嶅姟鍣ㄧ殑IP鎴栧煙鍚�:"

read mumjijiipaddress

echo

echo -n -e "璇疯緭鍏ヤ富鏈嶅姟鍣ㄦ祦鎺х鍙�:"

read mumjijiipport

echo

echo -n -e "璇疯緭鍏ヤ富鏈嶅姟鍣ㄧ殑鏁版嵁搴撳瘑鐮�:"

read mumjijisqlpass

echo

echo -n -e "璇疯緭鍏ュ綋鍓嶆湇鍔″櫒鏁版嵁搴撳瘑鐮�:"

read sbsonsqlpass

echo

echo "鎮ㄤ繚瀛樼殑閰嶇疆濡備笅锛�"

echo -e "\033[31m-------------------------------------------\033[0m"

echo "涓绘湇鍔″櫒缃戝潃:$mumjijiipaddress"

echo "涓绘湇鍔″櫒娴佹帶绔彛:$mumjijiipport"

echo "涓绘湇鍔″櫒鏁版嵁搴撳瘑鐮�:$mumjijisqlpass"

echo "褰撳墠鏈嶅姟鍣ㄦ暟鎹簱瀵嗙爜锛�$sbsonsqlpass"

echo -e "\033[31m-------------------------------------------\033[0m"

echo -e "\033[31m娉ㄦ剰锛歕033[0m\033[35m \033[0m"

echo -e "\033[33m濡備俊鎭棤璇鍥炶溅寮€濮嬮厤缃�.\033[0m"

echo -e "\033[33m濡傛灉淇℃伅鏈夐敊璇锋寜 Ctrl + c 閿粨鏉熷鎺ワ紝骞堕噸鏂版墽琛屽鎺ヨ剼鏈紒\033[0m"

echo -e "\033[35m鍥炶溅寮€濮嬫墽琛岄厤缃� >>>\033[0m"

read

echo "姝ｅ湪閰嶇疆鏁版嵁 璇风◢绛�..."

sed -i 's/localhost/'$mumjijiipaddress'/g' /home/wwwroot/default/config.php >/dev/null 2>&1

sed -i 's/'$sbsonsqlpass'/'$mumjijisqlpass'/g' /home/wwwroot/default/config.php >/dev/null 2>&1

sed -i 's/'$sbsonsqlpass'/'$mumjijisqlpass'/g' /etc/openvpn/xyr >/dev/null 2>&1

sed -i 's/localhost/'$mumjijiipaddress'/g' /etc/openvpn/xyr.config >/dev/null 2>&1

sed -i 's/'$sbsonsqlpass'/'$mumjijisqlpass'/g' /etc/openvpn/sqlmima >/dev/null 2>&1

echo

cd /etc/openvpn/

rm -rf ./disconnect.sh >/dev/null 2>&1

curl -O ${http}${host}${vpnfile}${dis}

chmod 0777 ./${dis} >/dev/null 2>&1

sed -i 's/192.168.1.1/'$mumjijiipaddress'/g' /etc/openvpn/disconnect.sh >/dev/null 2>&1

sed -i 's/:81/:'$mumjijiipport'/g' /etc/openvpn/disconnect.sh >/dev/null 2>&1

echo

echo "閲嶅惎鐩戞帶..."

/home/wwwroot/default/res/jiankong >>/home/wwwlog/jiankong.log 2>&1 &

/home/wwwroot/default/udp/jiankong >>/home/wwwlog/jiankong-udp.log 2>&1 &

vpn >/dev/null 2>&1

echo -e "\033[31m閰嶇疆瀹屾垚!\033[0m"

echo -e "\033[33m鎴愬姛涓庝富鏈嶅姟鍣↖P:$mumjijiipaddress 瀵规帴鎴愬姛\033[0m"

echo -e "\033[35m璇疯嚜琛屽埌涓绘湇鍔″櫒鍚庡彴娣诲姞褰撳墠鏈嶅姟鍣� $IP\033[0m"

exit 0;

fi

vpnportseetings

readytoinstall

newvpn

installlamp

webml

echo

echo "姝ｅ湪涓烘偍寮€鍚墍鏈夋湇鍔�..."

ovpn

webmlpass

pkgovpn

fi

fi

echo "$finishlogo";

rm -rf /etc/openvpn/ca >/dev/null 2>&1

return 1

}

main
exit 0;
