---
title: Définir l’étendue du déploiement E9-1-1 de Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Décisions nécessaires pour planifier un déploiement E9-1-1 dans Skype Business Server Enterprise Voice.
ms.openlocfilehash: 01b6b1656826977444928583ff08e8cb23b2982d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886288"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Définir l’étendue du déploiement E9-1-1 de Skype pour Business Server

Décisions nécessaires pour planifier un déploiement E9-1-1 dans Skype Business Server Enterprise Voice.

Avant de configurer Skype pour les entreprises pour E9-1-1, vous devez planifier votre déploiement E9-1-1. Voici certaines des questions que vous pouvez vous poser :

 **Quelles sont la stratégie de votre organisation et les obligations légales concernant E9-1-1 ?**

 Les obligations légales en matière d’E9-1-1 pour les PBX (appelés aussi systèmes téléphoniques multilignes, ou MLTS (Multi-line Telephone Systems) dans le langage E9-1-1) diffèrent d’un État à l’autre. Vous devez consulter votre équipe juridique de comprendre les obligations applicables à votre déploiement de Skype pour l’entreprise dans vos sites pertinents.

 **Quels secteurs de votre entreprise doivent être activés pour E9-1-1 ?**

 Vous pouvez activer E9-1-1 à des emplacements spécifiques ou dans toute l’entreprise. Par exemple, votre utilisation d’E9-1-1 peut varier selon les États ou pays/régions dans lesquels les bureaux de votre entreprise se trouvent, ou bien vous pouvez exclure les sites se trouvant en dehors des États-Unis.

 **Comment allez-vous déployer E9-1-1 sur des sites de succursale ?**

 La résistance des communications vocales est un concept qu’il est important de comprendre si vous déployez E9-1-1 sur un site de succursale. Si vous avez centralisé jonctions SIP E-9-1-1 et une panne de réseau étendu, clients connexion pas peut-être d’obtention d’un emplacement de service d’informations sur l’emplacement ou pour se connecter pour le fournisseur de services d’urgence. Skype pour les entreprises fournit plusieurs stratégies de gestion de la résilience vocale dans les succursales, y compris : ayant des réseaux de données résistantes, le déploiement d’une jonction SIP à chaque branche ou diffuser les appels d’urgence vers la passerelle locale pendant les pannes. Pour plus d’informations, voir [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **Allez-vous activer E9-1-1 pour les utilisateurs travaillant en dehors du réseau ?**

 Acquisition de l’emplacement automatique est disponible uniquement pour les clients situés à l’intérieur du réseau de l’organisation, afin que votre organisation doit décider si elle prendra en charge les appels E9-1-1 à partir de Skype pour les clients professionnels lors hors site. Par exemple, allez-vous autoriser les utilisateurs à passer des appels d’urgence quand ils travaillent de chez eux ou chez un client ? Si un client se trouve en dehors du réseau d’entreprise, il peut être configuré de sorte à inviter l’utilisateur à indiquer son emplacement. Cependant, les emplacements fournis par l’utilisateur ne peuvent pas être prévalidés par rapport au guide MSAG (Master Street Address Guide), le répartiteur du fournisseur de services d’urgence devra donc confirmer verbalement avec l’appelant la validité de son emplacement avant d’acheminer l’appel vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP).

> [!NOTE]
> Skype pour les clients d’entreprise d’utilisateurs qui se connectent au réseau de votre organisation à l’aide de VPN peut prendre les informations d’adresse IP internes, mais étant donné que ces adresses ne peut pas être utilisés pour identifier l’emplacement réel de l’utilisateur, il est essentiel que les sous-réseaux de réseau privé virtuel sont exclus à partir du service informations d’emplacement.

 **Voulez-vous que les appels d’urgence soient acheminés vers des sites en dehors des États-Unis ?**

 Vous voudrez peut-être que des zones de votre entreprise bénéficient du routage des appels d’urgence alors qu’elles ne disposent pas d’un fournisseur de services d’urgence (par exemple, des sites à l’étranger). Pour ce faire, créez un site, puis affectez des stratégies de voix aux sites qui utilisent le réseau RTC pour acheminer l’appel via une passerelle RTC locale.


