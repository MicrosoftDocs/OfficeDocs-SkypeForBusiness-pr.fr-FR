---
title: Définir l’étendue du déploiement de E9-1-1 dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Décisions nécessaires à la planification d’un déploiement E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: fa300ac2f4ba1c0d847abec138b6882e4f240831
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802464"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Définir l’étendue du déploiement de E9-1-1 dans Skype entreprise Server

Décisions nécessaires à la planification d’un déploiement E9-1-1 dans Skype entreprise Server Voice.

Avant de configurer Skype entreprise pour E9-1-1, vous devez planifier votre déploiement E9-1-1. Voici certaines des questions que vous pouvez vous poser :

 **Quelles sont les obligations légales et juridiques de votre organisation en matière de E9-1-1 ?**

 Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre. Reportez-vous à votre équipe légale pour comprendre les obligations qui pourraient s’appliquer à votre déploiement de Skype entreprise dans vos zones géographiques pertinentes.

 **Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**

 Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis.

 **Comment allez-vous déployer E9-1-1 sur des sites de succursale ?**

 La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale. Si vous avez centralisé des lignes SIP E-9-1-1 et une panne de réseau étendu (WAN), les clients qui se connectent risquent de ne pas être en mesure d’obtenir un emplacement à partir du service de coordonnées de l’emplacement ou de se connecter au fournisseur de services d’urgence. Skype entreprise fournit différentes stratégies de gestion de la résilience vocale dans les succursales, notamment : utilisation de réseaux de données résilients, déploiement d’une ligne SIP dans chaque succursale, ou transfert d’appels d’urgence vers la passerelle locale lors des pannes. Pour plus d’informations, reportez-vous à [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**

 L’acquisition automatique de l’emplacement est disponible uniquement pour les clients situés à l’intérieur du réseau de l’organisation, afin que votre organisation puisse prendre en charge les appels E9-1-1 passés à partir de clients Skype entreprise sur site. Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ? Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement. Cependant, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).

> [!NOTE]
> Les clients Skype entreprise d’utilisateurs qui se connectent au réseau de votre organisation à l’aide d’un VPN peuvent capter les informations d’adresse IP interne, mais ces adresses ne peuvent pas être utilisées pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux VPN soient exclus. à partir du service d’information d’emplacement.

 **Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**

 Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau RTC pour acheminer l’appel via une passerelle RTC locale.


