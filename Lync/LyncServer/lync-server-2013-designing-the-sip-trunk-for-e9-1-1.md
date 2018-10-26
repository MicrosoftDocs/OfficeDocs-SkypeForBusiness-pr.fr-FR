---
title: 'Lync Server 2013 : Conception de la jonction SIP pour E9-1-1'
TOCTitle: Conception de la jonction SIP pour E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398323(v=OCS.15)
ms:contentKeyID: 49297185
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conception de la jonction SIP pour E9-1-1 dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server utilise les jonctions SIP pour connecter un appel d’urgence au fournisseur du service E9-1-1. Vous pouvez configurer des jonctions SIP de services d’urgence pour le service E9-1-1 au niveau d’un site central, de plusieurs sites centraux ou de chaque site de succursale. Cependant, si la liaison de réseau étendu (WAN) entre le site de l’appelant et le site qui héberge la jonction SIP de service d’urgence n’est pas disponible, tout appel passé par un utilisateur au niveau du site déconnecté nécessitera un enregistrement d’utilisation téléphonique spécifique dans la stratégie de voix de l’utilisateur qui acheminera l’appel au centre d’intervention en cas d’appels d’urgence via la passerelle RTC. Il en va de même si les limites relatives aux appels simultanés du service Contrôle d’admission des appels sont appliquées.

> [!NOTE]  
> Il existe deux façons d’implémenter une liaison SIP dans un environnement Lync Server :
> <ul>
> <li><p>en utilisant des serveurs de médiation multirésidents qui tirent parti de leurs interfaces routées publiquement vers l’extérieur pour communiquer avec le fournisseur de jonctions SIP ;</p></li>
> <li><p>en utilisant un contrôleur SBC (Session Border Controller) local pour offrir un point de démarcation sécurisé entre les serveurs de médiation et les services du fournisseur de jonctions SIP.</p></li></ul>
> Si vous choisissez cette dernière méthode, assurez-vous que la marque et le modèle du contrôleur SBC que vous choisissez ont été certifiés et que celui-ci prend en charge le transfert des données d’emplacement PIDF-LO (Presence Information Data Format Location Object) dans le cadre de sa requête SIP INVITE. Dans le cas contraire, les appels parviennent au fournisseur de services d’urgence sans leurs informations d’emplacement. Pour plus d’informations sur les SBC certifiés, reportez-vous à la description de l’infrastructure agréée pour Microsoft Lync à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</a>.<br />
> Les fournisseurs de services E9-1-1 vous permettent d’accéder à une paire de contrôleurs SBC à des fins de redondance. Vous devez prendre plusieurs décisions concernant la topologie du serveur de médiation et la configuration du routage des appels. Allez-vous traiter les deux contrôleurs SBC comme des homologues égaux et utiliser le routage par tourniquet (round robin) pour les appels qu’ils s’échangent, ou allez-vous désigner l’un des contrôleurs SBC en tant que serveur principal et l’autre en tant que serveur secondaire ?


Pour plus d’informations sur le déploiement d’une jonction SIP dans Lync Server, reportez-vous à [Implémentation d’une jonction SIP dans Lync Server 2013](lync-server-2013-how-do-i-implement-sip-trunking.md). Pour faciliter le déploiement de jonctions SIP pour E9-1-1, répondez d’abord aux questions suivantes.

  - **Devez-vous déployer la jonction SIP sur une connexion en bail dédiée ou une connexion Internet partagée ?**  
    Il est important que les appels d’urgence se connectent en permanence. Une ligne dédiée fournit une connexion qui n’est pas préemptée par un autre trafic réseau. En outre, elle permet d’implémenter la qualité de service (QoS). N’oubliez pas que si vous vous connectez à des fournisseurs de services d’urgence via le réseau Internet public et si vous devez garantir la confidentialité des appels d’urgence, un chiffrement IPsec est nécessaire.

<!-- end list -->

  - **Votre déploiement E9-1-1 est-il conçu pour une tolérance aux défaillances ?**  
    Puisqu’il s’agit d’une solution d’urgence, la résistance est importante. Déployez vos serveurs de médiation principal et secondaire, ainsi que vos jonctions SIP, à des emplacements tolérants aux défaillances. Il est conseillé de déployer le serveur de médiation principal le plus près possible des utilisateurs qu’il prend en charge et d’acheminer les appels de basculement via le serveur de médiation secondaire (situé à un autre emplacement géographique).

<!-- end list -->

  - **Devez-vous déployer une jonction SIP distincte pour chaque succursale ?**  
    Lync Server fournit plusieurs stratégies permettant de gérer la résistance des communications vocales des sites de succursale, notamment : l’utilisation de réseaux de données résilients, le déploiement d’une jonction SIP dans chaque succursale ou le transfert des appels vers la passerelle lors de pannes. Pour plus d’informations, reportez-vous à [Jonction SIP de site de succursale dans Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **Le contrôle d’admission des appels (CAC) est-il activé ?**  
    Lync Server ne gère pas les appels d’urgence différemment des appels ordinaires. Pour cette raison, la gestion de la bande passante ou le service Contrôle d’admission des appels peut avoir un impact négatif sur une configuration E9-1-1. Les appels d’urgence sont bloqués ou acheminés vers la passerelle RTC locale si un service Contrôle d’admission des appels est activé et si la limite configurée est dépassée sur une liaison où les appels d’urgence sont acheminés. Comme indiqué précédemment dans cette rubrique, ce type d’appel ne dispose pas de données d’emplacement et doit être acheminé manuellement vers le centre d’intervention en cas d’appels d’urgence.

