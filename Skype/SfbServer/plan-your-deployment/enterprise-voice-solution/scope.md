---
title: Définir l’étendue du déploiement E9-1-1 dans Skype Entreprise Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Décisions nécessaires à la planification d’un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: bec80e94c5bc2044359875f7c56f92a1348464c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813424"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Définir l’étendue du déploiement E9-1-1 dans Skype Entreprise Server

Décisions nécessaires à la planification d’un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.

Avant de configurer Skype Entreprise pour E9-1-1, vous devez planifier votre déploiement E9-1-1. Voici certaines des questions que vous pouvez vous poser :

 **Quelles sont les obligations légales et de stratégie de votre organisation concernant E9-1-1 ?**

 Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre. Vous devez consulter votre équipe juridique pour comprendre les obligations qui peuvent s’appliquer à votre déploiement de Skype Entreprise dans vos zones géographiques pertinentes.

 **Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**

 Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis.

 **Comment allez-vous déployer E9-1-1 sur des sites de succursales ?**

 La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale. Si vous avez centralisé des connexions SIP E-9-1-1 et qu’une panne de réseau wan se produit, il se peut que les clients qui se connectent ne puissent pas obtenir un emplacement à partir du service Informations sur l’emplacement ou se connecter au fournisseur de services d’urgence. Skype Entreprise fournit plusieurs stratégies de gestion de la résistance vocale dans les succursales, notamment : avoir des réseaux de données résilients, déployer une branche SIP dans chaque succursale ou faire passer des appels d’urgence vers la passerelle locale en cas de panne. Pour plus d’informations, voir [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**

 L’acquisition automatique d’emplacement est disponible uniquement pour les clients situés au sein du réseau de l’organisation. Votre organisation doit donc décider si elle prendra en charge les appels E9-1-1 effectués à partir de clients Skype Entreprise hors site. Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ? Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement. Toutefois, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).

> [!NOTE]
> Les clients Skype Entreprise des utilisateurs qui se connectent au réseau de votre organisation à l’aide de VPN peuvent récupérer des informations d’adresse IP internes, mais comme ces adresses ne peuvent pas être utilisées pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux VPN soient exclus du service Informations d’emplacement.

 **Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**

 Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau PSTN pour acheminer l’appel via une passerelle PSTN locale.


