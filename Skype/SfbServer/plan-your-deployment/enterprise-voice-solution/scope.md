---
title: Définir l’étendue du déploiement E9-1-1 dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Décisions nécessaires à la planification d’un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: a1757477d9d4de2a0e26c3490bb6214e6c14e1e9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836246"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Définir l’étendue du déploiement E9-1-1 dans Skype Entreprise Server

Décisions nécessaires à la planification d’un déploiement E9-1-1 dans Skype Entreprise Server Voix Entreprise.

Avant de configurer Skype Entreprise pour E9-1-1, vous devez planifier votre déploiement E9-1-1. Voici certaines des questions que vous pouvez vous poser :

 **Quelles sont les obligations légales et de stratégie de votre organisation concernant E9-1-1 ?**

 Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre. Vous devez consulter votre équipe juridique pour comprendre les obligations qui peuvent s’appliquer à votre déploiement de Skype Entreprise dans vos zones géographiques pertinentes.

 **Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**

 Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis.

 **Comment allez-vous déployer E9-1-1 sur des sites de succursales ?**

 La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale. Si vous avez centralisé des connexions SIP E-9-1-1 et qu’une panne de réseau wan se produit, les clients qui se connectent risquent de ne pas pouvoir obtenir un emplacement à partir du service Informations sur l’emplacement ou se connecter au fournisseur de services d’urgence. Skype Entreprise propose plusieurs stratégies de gestion de la résistance vocale dans les succursales, notamment : avoir des réseaux de données résilients, déployer une branche SIP dans chaque succursale ou faire passer des appels d’urgence vers la passerelle locale en cas de panne. Pour plus d’informations, voir [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).

 **Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**

 L’acquisition automatique d’emplacement est disponible uniquement pour les clients situés au sein du réseau de l’organisation. Votre organisation doit donc décider si elle prendra en charge les appels E9-1-1 effectués à partir de clients Skype Entreprise en dehors de l’organisation. Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ? Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement. Toutefois, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).

> [!NOTE]
> Skype Entreprise clients d’utilisateurs qui se connectent au réseau de votre organisation à l’aide d’un VPN peuvent récupérer des informations d’adresse IP internes, mais comme ces adresses ne peuvent pas être utilisées pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux VPN soient exclus du service Informations d’emplacement.

 **Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**

 Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau PSTN pour acheminer l’appel via une passerelle PSTN locale.