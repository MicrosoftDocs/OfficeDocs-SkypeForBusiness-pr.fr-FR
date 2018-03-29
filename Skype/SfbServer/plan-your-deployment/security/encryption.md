---
title: Chiffrement pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/15/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype pour Business Server 2015 utilise TLS et MTLS pour chiffrer les messages instantanés. L’ensemble du trafic serveur à serveur nécessite MTLS, et ce que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre du réseau interne. Lorsque la connexion Skype pour Business Server 2015 à 3 systèmes IPPBX de tiers ou les SIP trunks TLS est facultatif mais fortement recommandé entre le serveur de médiation et la passerelle multimédia. Si TLS est configuré sur cette liaison, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat auprès d’une autorité de certification qui est approuvée par le serveur de médiation.
ms.openlocfilehash: bf17f2c8ff8180fa5622957c665da3f4608ca833
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="encryption-for-skype-for-business-server-2015"></a>Chiffrement pour Skype Entreprise Server 2015
 
Skype pour Business Server 2015 utilise TLS et MTLS pour chiffrer les messages instantanés. L’ensemble du trafic serveur à serveur nécessite MTLS, et ce que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre du réseau interne. Lorsque la connexion Skype pour Business Server 2015 à 3 systèmes IPPBX de tiers ou les SIP trunks TLS est facultatif mais fortement recommandé entre le serveur de médiation et la passerelle multimédia. Si TLS est configuré sur cette liaison, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat auprès d’une autorité de certification qui est approuvée par le serveur de médiation.
  
> [!NOTE]
> Un avis de sécurité relatif à SSL 3.0 a été publié en 2014. Désactiver SSL 3.0 dans Skype pour Business Server 2015 est une option de prise en charge. Pour en savoir plus sur l’avis de sécurité, voir [désactivation de SSL 3.0 dans Lync Server 2013 et Skype pour Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/). 
  
> [! NOTE de sécurité] afin de garantir le protocole de cryptage plus puissant est utilisé, Skype pour Business Server 2015 offre aux clients des protocoles de cryptage TLS dans l’ordre suivant : **TLS 1.2, TLS 1.1 et TLS 1.0**. TLS est un aspect critique de Skype pour Business Server 2015 et il est donc nécessaire afin de maintenir un environnement pris en charge. 
  
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
> Si vous implémentez un environnement hybride, vous devez également modifier le Skype Business Server 2015 niveau de chiffrement. Par défaut, ce paramètre est défini sur Requis. Vous devez modifier ce paramètre sur pris en charge à l’aide de la Skype pour Business Server Management Shell. Pour plus d’informations sur la configuration hybride, voir [déplacer les utilisateurs de Skype pour Business en ligne sur le site](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md) dans la documentation de déploiement.
  
## <a name="fips"></a>FIPS

Skype pour Business Server 2015 et 2016 de Microsoft Exchange Server fonctionne avec la prise en charge des algorithmes de traitement Standard FIPS (Federal Information) 140-2 si les systèmes d’exploitation Windows Server sont configurés pour utiliser la norme FIPS 140-2 algorithmes par système cryptographie. Pour implémenter la prise en charge FIPS, vous devez configurer chaque serveur exécutant Skype pour 2015 de serveur d’entreprise prendre en charge.
  

