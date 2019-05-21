---
title: Chiffrement pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype entreprise Server utilise TLS et MTLS pour chiffrer les messages instantanés. L’ensemble du trafic serveur à serveur nécessite MTLS, et ce que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre du réseau interne. Lors de la connexion de Skype entreprise Server à des systèmes IPPBX tiers ou des Trunks SIP, le protocole TLS est facultatif, mais fortement recommandé entre le serveur de médiation et la passerelle multimédia. Si TLS est configuré sur cette liaison, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat provenant d’une autorité de certification approuvée par le serveur de médiation.
ms.openlocfilehash: 3aadc51dff7fafe32ea929cdec3d4f2f03ee92fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296916"
---
# <a name="encryption-for-skype-for-business-server"></a>Chiffrement pour Skype entreprise Server
 
Skype entreprise Server utilise TLS et MTLS pour chiffrer les messages instantanés. L’ensemble du trafic serveur à serveur nécessite MTLS, et ce que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre du réseau interne. Lors de la connexion de Skype entreprise Server à des systèmes IPPBX tiers ou des Trunks SIP, le protocole TLS est facultatif, mais fortement recommandé entre le serveur de médiation et la passerelle multimédia. Si TLS est configuré sur cette liaison, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat provenant d’une autorité de certification approuvée par le serveur de médiation.
  
> [!NOTE]
> Un avis de sécurité relatif à SSL 3.0 a été publié en 2014. La désactivation de SSL 3,0 dans Skype entreprise Server 2015 est une option prise en charge. Pour en savoir plus sur l’avis de sécurité, voir [désactivation de la 3,0 SSL dans Lync Server 2013 et Skype entreprise Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Note de sécurité:** Pour vous assurer que le protocole cryptographique le plus puissant est utilisé, Skype entreprise Server 2015 offrira des protocoles de chiffrement TLS dans l’ordre suivant pour les clients: **tls 1,2, tls 1,1, tls 1,0**. Le protocole TLS est un aspect essentiel de Skype entreprise Server 2015 et, par conséquent, il est requis pour gérer un environnement pris en charge.<br/>
**Note de sécurité:** Pour vous assurer que le protocole cryptographique le plus puissant est utilisé, Skype entreprise Server 2019 offrira des protocoles de chiffrement TLS dans l’ordre suivant pour les clients: **tls 1,3, tls 1,2**. Le protocole TLS est un aspect essentiel de Skype entreprise Server 2019 et, par conséquent, il est requis pour gérer un environnement pris en charge. 
  
Le tableau suivant résume les exigences de protocole pour chaque type de trafic. 
  
**Protection du trafic**

|**Type de trafic**|**Protégé par**|
|:-----|:-----|
|Serveur à serveur  <br/> |MTLS  <br/> |
|Client à serveur  <br/> |TLS  <br/> |
|Messagerie instantanée et présence  <br/> |TLS   <br/> |
|Partage multimédia audio, vidéo et de bureau  <br/> |SRTP  <br/> |
|Partage du bureau (signalisation)  <br/> |TLS  <br/> |
|Conférence web  <br/> |TLS  <br/> |
|Téléchargement de contenu de réunion, téléchargement de carnet d’adresses, développement de groupe de distribution  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Chiffrement multimédia

Le trafic multimédia est chiffré à l'aide du protocole SRTP (Secure Real-time Transport Protocol), un profil du protocole RTP (Real-Time Transport Protocol) qui offre confidentialité, authentification et protection contre les attaques sur le trafic RTP. De plus, les données multimédias acheminées dans les deux directions entre le serveur de médiation et son tronçon suivant interne sont également chiffrées avec SRTP. Les données multimédias acheminées dans les deux directions entre le serveur de médiation et une passerelle multimédia sont également chiffrées et recommandées. Le serveur de médiation peut prendre en charge le chiffrement sur la passerelle multimédia, mais la passerelle doit prendre en charge MTLS et le stockage d’un certificat.
  
> [!NOTE]
> Pour plus d’informations sur la configuration d’une connexion hybride, voir [planifier une connectivité hybride](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

Les algorithmes 140-2 FIPS Server et Microsoft Exchange Server 2016 prennent en charge les algorithmes de gestion des informations fédérales si les systèmes d’exploitation Windows Server sont configurés pour utiliser les algorithmes 140-2 FIPS pour le chiffrement du système. . Pour mettre en œuvre la prise en charge du FIPS, vous devez configurer chaque serveur exécutant Skype entreprise Server pour le prendre en charge.
  

