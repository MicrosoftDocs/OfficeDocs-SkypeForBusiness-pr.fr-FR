---
title: Chiffrement pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype Entreprise Server utilise TLS et MTLS pour chiffrer les messages instantanés. Tout le trafic de serveur à serveur nécessite MTLS, que le trafic soit limité au réseau interne ou qu’il traverse le périmètre du réseau interne. Lors de la connexion de Skype Entreprise Server à des systèmes IPPBX tiers ou des connexions SIP TLS est facultatif, mais fortement recommandé entre le serveur de médiation et la passerelle multimédia. Si TLS est configuré sur ce lien, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat d’une ca qui est approuvé par le serveur de médiation.
ms.openlocfilehash: 48af03d7f6aed5b744ad4e0c460622194a87d96e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832204"
---
# <a name="encryption-for-skype-for-business-server"></a>Chiffrement pour Skype Entreprise Server
 
Skype Entreprise Server utilise TLS et MTLS pour chiffrer les messages instantanés. Tout le trafic de serveur à serveur nécessite MTLS, que le trafic soit limité au réseau interne ou qu’il traverse le périmètre du réseau interne. Lors de la connexion de Skype Entreprise Server à des systèmes IPPBX tiers ou des trunks SIP TLS est facultatif, mais fortement recommandé entre le serveur de médiation et la passerelle multimédia. Si TLS est configuré sur ce lien, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat d’une ca qui est approuvé par le serveur de médiation.
  
> [!NOTE]
> Un avis de sécurité concernant SSL 3.0 a été publié en 2014. La désactivation de SSL 3.0 dans Skype Entreprise Server 2015 est une option prise en charge. Pour en savoir plus sur l’avis de sécurité, voir [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Note de sécurité :** Pour s’assurer que le protocole de chiffrement le plus fort est utilisé, Skype Entreprise Server 2015 proposera des protocoles de chiffrement TLS dans l’ordre suivant aux clients : **TLS 1.2, TLS 1.1, TLS 1.0**. TLS est un aspect essentiel de Skype Entreprise Server 2015 et est donc nécessaire pour maintenir un environnement pris en charge.<br/>
**Note de sécurité :** Pour s’assurer que le protocole de chiffrement le plus fort est utilisé, Skype Entreprise Server 2019 proposera des protocoles de chiffrement TLS dans l’ordre suivant aux clients : **TLS 1.3, TLS 1.2**. TLS est un aspect essentiel de Skype Entreprise Server 2019 et est donc nécessaire pour maintenir un environnement pris en charge. 
  
Le tableau suivant résume les protocoles requis pour chaque type de trafic. 
  
**Protection du trafic**

|**Type de trafic**|**Protégé par**|
|:-----|:-----|
|Serveur à serveur  <br/> |MTLS  <br/> |
|Client à serveur  <br/> |TLS  <br/> |
|Messagerie instantanée et présence  <br/> |TLS  <br/> |
|Partage de données audio, vidéo ou du Bureau  <br/> |SRTP  <br/> |
|Partage du Bureau (signalisation)  <br/> |TLS  <br/> |
|Conférence web  <br/> |TLS  <br/> |
|Téléchargement de contenu de réunion, de carnets d’adresses, développement des groupes de distribution  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Chiffrement des données multimédias

Le trafic multimédia est chiffré à l’aide du protocole SRTP (Secure RTP), un profil du protocole RTP (Real-Time Transport Protocol). De plus, le flux de contenu entrant dans les deux directions entre le serveur de médiation et son saut interne suivant est également chiffré à l’aide de SRTP. Le trafic multimédia qui circule dans les deux sens entre le serveur de médiation et une passerelle multimédia est éventuellement chiffré et recommandé. Le serveur de médiation peut prendre en charge le chiffrement sur la passerelle multimédia mais, dans ce cas, celle-ci doit prendre en charge MTLS et le stockage d’un certificat.
  
> [!NOTE]
> Pour plus d’informations sur la configuration hybride, voir [Planifier la connectivité hybride.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)
  
## <a name="fips"></a>FIPS

Skype Entreprise Server et Microsoft Exchange Server 2016 fonctionnent avec la prise en charge des algorithmes FIPS (Federal Information Processing Standard) 140-2 si les systèmes d’exploitation Windows Server sont configurés pour utiliser les algorithmes FIPS 140-2 pour le chiffrement du système. Pour implémenter la prise en charge fiPS, vous devez configurer chaque serveur exécutant Skype Entreprise Server pour la prendre en charge.
  

