---
title: Chiffrement pour Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype pour Business Server utilise TLS et MTLS pour chiffrer les messages instantanés. L’ensemble du trafic serveur à serveur nécessite MTLS, et ce que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre du réseau interne. Lorsque la connexion Skype pour Business Server 3ème systèmes tiers de IPPBX ou jonctions SIP TLS est facultatif mais fortement recommandé entre le serveur de médiation et passerelle multimédia. Si TLS est configuré sur cette liaison, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat à partir d’une autorité de certification approuvée par le serveur de médiation.
ms.openlocfilehash: ff2aa0a3d0727aa5ed579413fe03593568f9f773
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240894"
---
# <a name="encryption-for-skype-for-business-server"></a>Chiffrement pour Skype pour Business Server
 
Skype pour Business Server utilise TLS et MTLS pour chiffrer les messages instantanés. L’ensemble du trafic serveur à serveur nécessite MTLS, et ce que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre du réseau interne. Lorsque la connexion Skype pour Business Server pour les systèmes tiers IPPBX ou jonctions SIP TLS est facultatif mais fortement recommandé entre le serveur de médiation et passerelle multimédia. Si TLS est configuré sur cette liaison, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat à partir d’une autorité de certification approuvée par le serveur de médiation.
  
> [!NOTE]
> Un avis de sécurité relatif à SSL 3.0 a été publié en 2014. Désactivation de SSL 3.0 dans Skype pour Business Server 2015 est une option de prise en charge. Pour en savoir plus sur l’avis de sécurité, voir [désactivation SSL 3.0 dans Lync Server 2013 et Skype pour Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Remarque sur la sécurité :** Pour vérifier que le protocole de chiffrement puissant est utilisé, Skype pour Business Server 2015 offre les protocoles de chiffrement TLS dans l’ordre suivant aux clients : **TLS 1.2, TLS 1.1, TLS 1.0**. TLS est un aspect critique de Skype pour Business Server 2015 et par conséquent, il est nécessaire afin de conserver un environnement pris en charge.<br/>
**Remarque sur la sécurité :** Pour vérifier que le protocole de chiffrement puissant est utilisé, Skype pour Business Server 2019 offre les protocoles de chiffrement TLS dans l’ordre suivant aux clients : **1.3 TLS, TLS 1.2**. TLS est un aspect critique de Skype pour Business Server 2019 et par conséquent, il est nécessaire afin de conserver un environnement pris en charge. 
  
Le tableau suivant résume les exigences de protocole pour chaque type de trafic. 
  
**Protection du trafic**

|**Type de trafic**|**Protégé par**|
|:-----|:-----|
|Serveur à serveur  <br/> |MTLS  <br/> |
|Client à serveur  <br/> |TLS  <br/> |
|Messagerie instantanée et présence  <br/> |TLS  <br/> |
|Partage multimédia audio, vidéo et de bureau  <br/> |SRTP  <br/> |
|Partage du bureau (signalisation)  <br/> |TLS  <br/> |
|Conférence web  <br/> |TLS  <br/> |
|Téléchargement de contenu de réunion, téléchargement de carnet d’adresses, développement de groupe de distribution  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Chiffrement multimédia

Le trafic multimédia est chiffré à l'aide du protocole SRTP (Secure Real-time Transport Protocol), un profil du protocole RTP (Real-Time Transport Protocol) qui offre confidentialité, authentification et protection contre les attaques sur le trafic RTP. De plus, les données multimédias acheminées dans les deux directions entre le serveur de médiation et son tronçon suivant interne sont également chiffrées avec SRTP. Les données multimédias acheminées dans les deux directions entre le serveur de médiation et une passerelle multimédia sont également chiffrées et recommandées. Le serveur de médiation peut prendre en charge le chiffrement sur la passerelle multimédia, mais la passerelle doit prendre en charge MTLS et le stockage d’un certificat.
  
> [!NOTE]
> Si vous implémentez un environnement hybride, vous devez également modifier le Skype Business Server niveau de chiffrement. Par défaut, ce paramètre est défini sur Requis. Vous devez modifier ce paramètre sur pris en charge à l’aide de la Skype pour Business Server Management Shell. Pour plus d’informations sur la configuration hybride, consultez [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) ou [Skype pour les solutions Business Server 2019 hybride](../../../SfBServer2019/hybrid/hybrid-solutions.md) dans la documentation de déploiement.
  
## <a name="fips"></a>FIPS

Skype pour Business Server et Microsoft Exchange Server 2016 fonctionnent avec prise en charge pour les algorithmes de traitement Standard FIPS (Federal Information) 140-2 si les systèmes d’exploitation Windows Server sont configurés pour utiliser FIPS 140-2 algorithmes pour le chiffrement du système . Pour implémenter la prise en charge FIPS, vous devez configurer chaque serveur qui exécute Skype pour Business Server prennent en charge.
  

