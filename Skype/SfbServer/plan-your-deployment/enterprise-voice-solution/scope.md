---
title: Définition de l’étendue du déploiement E9-1-1 dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Décisions nécessaires à la planification d’un déploiement E9-1-1 dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: f81a2c56642557bf92a965de025aecbdbcadadcd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server-2015"></a>Définition de l’étendue du déploiement E9-1-1 dans Skype Entreprise Server 2015
 
Décisions nécessaires à la planification d’un déploiement E9-1-1 dans Skype pour Business Server Voix Entreprise.
  
Avant de configurer Skype pour entreprise pour E9-1-1, vous devez planifier votre déploiement E9-1-1. Voici certaines des questions que vous pouvez vous poser :
  
 **Quelles sont la stratégie de votre entreprise et les obligations légales en matière de E9-1-1 ?**
  
 Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre. Vous devez consulter votre équipe juridique pour comprendre les obligations qui peuvent s’appliquer à votre déploiement de Skype pour entreprise dans vos zones géographiques pertinentes.
    
 **Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**
  
 Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis. 
    
 **Comment allez-vous déployer E9-1-1 sur des sites de succursale ?**
  
 La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale. Si vous avez centralisée E-9-1-1 SIP de puits et une panne du réseau étendue se produit, la connexion de clients peut-être pas pour obtenir un emplacement de service d’informations d’emplacement ou pour se connecter au fournisseur de service des services d’urgence. Skype pour entreprise fournit plusieurs stratégies pour gérer la résilience vocale dans les succursales, y compris : ayant des réseaux de données robuste, le déploiement d’un SIP trunk dans chaque succursale ou diffuser des appels d’urgence pour la passerelle locale pendant les pannes. Pour plus d’informations, consultez [planification de la résilience vocale-Site de la succursale](http://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).
    
 **Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**
  
 Acquisition de localisation automatique est disponible uniquement pour les clients situés à l’intérieur du réseau de l’organisation, afin que votre organisation doit décider si elle prendra en charge des appels E9-1-1 à partir de Skype pour les clients d’entreprise lors de lors d’un déplacement. Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ? Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement. Cependant, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).
    
> [!NOTE]
> Skype pour les clients d’entreprise d’utilisateurs qui se connectent au réseau de votre organisation à l’aide de VPN peut récupérer les informations d’adresse IP internes, mais étant donné que ces adresses ne peuvent pas être utilisées pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux VPN sont exclus. à partir du service d’informations d’emplacement. 
  
 **Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**
  
 Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau RTC pour acheminer l’appel via une passerelle RTC locale.
    

