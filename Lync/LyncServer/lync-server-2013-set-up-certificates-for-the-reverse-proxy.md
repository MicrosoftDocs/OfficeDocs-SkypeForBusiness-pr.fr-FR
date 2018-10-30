---
title: 'Lync Server 2013 : Configuration des certificats pour le serveur proxy inverse'
TOCTitle: Configuration des certificats pour le serveur proxy inverse
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412938(v=OCS.15)
ms:contentKeyID: 49298714
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des certificats pour le serveur proxy inverse dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Chaque serveur de proxy inverse nécessite un certificat de serveur web à la disposition du service d’écoute. Le certificat de serveur web doit être émis par une autorité de certification publique.

Pour plus d’informations à ce sujet et sur les certificats requis, reportez-vous à [Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

## Pour configurer un certificat de services web pour le serveur proxy inverse

  - Votre serveur de proxy inverse doit déjà avoir été configuré et la configuration du certificat de services web doit avoir eu lieu simultanément. Si rien de tout cela n’a été fait avant d’entamer le déploiement de vos serveurs Edge, suivez les procédures décrites dans la section [Configuration des serveurs proxy inverses pour Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) pour créer une demande et installer le certificat de services web. Ensuite, créez chaque règle de publication web et configurez-la pour pouvoir utiliser le certificat.

