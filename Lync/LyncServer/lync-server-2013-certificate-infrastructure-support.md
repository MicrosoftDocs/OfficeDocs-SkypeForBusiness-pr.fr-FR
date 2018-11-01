---
title: Prise en charge des infrastructures de certificat dans Lync Server 2013
TOCTitle: Prise en charge des infrastructures de certificat
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425950(v=OCS.15)
ms:contentKeyID: 49297087
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge des infrastructures de certificat dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-07_

Lync Server 2013 nécessite une infrastructure à clé publique (PKI, Public Key Infrastructure) pour la prise en charge des connexions TLS (Transport Layer Security) et MTLS (Mutual TLS). Par défaut, Lync Server 2013 est configuré pour utiliser TLS pour les connexions client à serveur. MTLS est utilisé pour les connexions entre serveurs.

Les certificats MTLS doivent être émis par des autorités de certification approuvées pour Lync Server 2013. Lync Server prend en charge les certificats émis à partir des autorités de certification suivantes :

  - Certificats émis par une autorité de certification interne :
    
      - Autorité de certification système d’exploitation Windows Server 2003
    
      - Autorité de certification du système d’exploitation Windows Server 2008
    
      - Autorité de certification du système d’exploitation Windows Server 2008 R2
    
      - Autorité de certification du système d’exploitation Windows Server 2012
    
      - Autorité de certification du système d’exploitation Windows Server 2012 R2

  - Certificats émis par une autorité de certification publique

Les communications avec d’autres applications et serveurs, comme Exchange 2013, nécessitent un certificat qui soit pris en charge par les autres applications et produits. Pour la version 2013, Lync Server 2013 et les autres produits serveur Microsoft, dont Exchange 2013 et SharePoint Server, prennent en charge le protocole OAuth (Open Authorization) pour l’authentification et l’autorisation de serveur à serveur. Pour plus d’informations, reportez-vous à [Gestion de l’authentification serveur à serveur (Oauth) et des applications partenaires dans Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou des opérations.

Pour les connexions établies à partir de clients exécutant système d’exploitation Windows 7, système d’exploitation Windows Server 2008 R2 et Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 inclut la prise en charge (mais ne nécessite pas) de certificats signés à l’aide de la fonction de hachage de chiffrement SHA-256. Pour permettre la prise en charge de l’accès externe via SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.

Pour plus d’informations sur les exigences relatives aux certificats, reportez-vous à [Configuration requise pour les infrastructures de certificat pour Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation de caractères génériques avec les certificats, reportez-vous à [Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) dans la documentation de prise en charge.

