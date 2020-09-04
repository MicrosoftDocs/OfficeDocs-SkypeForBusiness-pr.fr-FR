---
title: Planification pour sites PSTN Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lisez cette rubrique pour découvrir comment planifier vos sites PSTN de Cloud Connector Edition afin de garantir un acheminement des appels efficace et rentable.
ms.openlocfilehash: 3b4320e12a87c771e28fce445102327c7783a5d2
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358800"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planification pour sites PSTN Cloud Connector Edition

> [!Important]
> La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online. Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Lisez cette rubrique pour découvrir comment planifier vos sites PSTN de Cloud Connector Edition afin de garantir un acheminement des appels efficace et rentable.
  
Cette rubrique décrit ce que vous devez savoir sur la version Cloud Connector et l’acheminement des appels afin de pouvoir planifier les sites RTC de Cloud Connector. Un site RTC est une combinaison de plusieurs Appliances Cloud Connector déployées au même emplacement, avec des passerelles RTC communes connectées à ces appareils. Cette rubrique décrit la configuration de votre topologie de site Cloud Connector afin de s’assurer que les sites Cloud Connector peuvent gérer le routage entrant et sortant pour tous les utilisateurs affectés à un site de la manière la plus rentable et la plus efficace possible. Pour plus d’informations sur Cloud Connector et les avantages des sites RTC, lisez la rubrique [plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Routage des appels et des sites RTC Cloud Connector

Les sites RTC Cloud Connector sont des structures de topologie créées pour éviter les tarifs superflus et les tarifs interpaysaux, et pour garantir que les appels d’urgence sortants sont acheminés vers la jonction appropriée. Pour garantir un routage efficace et efficace des appels, y compris des appels vers les services d’urgence, vous devez planifier avec soin vos sites RTC et la façon dont les utilisateurs sont affectés à chaque site. 
  
Dans le cadre de votre planification de Cloud Connector, il est essentiel que vous discutiez avec vos transporteurs de l’emplacement de vos bureaux et de vos utilisateurs et que les jonctions RTC soient terminées à partir de l’opérateur. Vous devez collaborer avec vos opérateurs pour déterminer la façon dont les appels d’urgence peuvent être acheminés, puis utiliser ces informations pour définir les sites RTC de Cloud Connector et affecter des utilisateurs aux sites appropriés. Par exemple, vous devez vous assurer que les jonctions qui se terminent dans un centre de contenu où le site RTC est étiré sont configurées pour gérer le routage entrant et sortant pour tous les numéros attribués aux utilisateurs de ce site. 
  
Chaque appliance Cloud Connector peut être connectée à plusieurs passerelles IP, PBX IP ou contrôleurs de frontière de session (SBC). Étant donné que les passerelles et les PBX sont connectés à des jonctions de télécommunications (jonctions PRI ou SIP), les appliances Cloud Connector sont logiquement connectées à des jonctions RTC pour les appels entrants et sortants. Avec Cloud Connector et la connectivité RTC locale, vous obtenez la jonction et les numéros de téléphone associés de votre opérateur local. Si votre entreprise est une grande entreprise, vous pouvez avoir plusieurs opérateurs, en particulier si votre entreprise s’étend sur plus d’une ville, d’un État ou d’un pays. Étant donné que votre opérateur est propriétaire du numéro de téléphone, le transporteur est responsable de la gestion des appels d’urgence.
  
Skype entreprise Online traite tous les équipements Cloud Connector dans un site équitablement et achemine les appels sortants en fonction de la rotation des appliances Cloud Connector dans le même site. Chaque Cloud Connector dans un site est relié au même ensemble de jonctions RTC (entièrement maillées). Étant donné que chaque utilisateur est associé à un site RTC de Cloud Connector, tout appel sortant provenant de cet utilisateur (normal ou d’urgence) sera affecté à l’un des appareils Cloud Connector dans le site RTC auquel l’utilisateur est associé. 
  
Cloud Connector effectue le routage des appels statiques vers ses passerelles IP connectées, les PBX IP, les jonctions PSTN ou les jonctions RTC directes. Cloud Connector n’est pas encore capable de routage dynamique vers une jonction basée sur la destination (pour un routage moins onéreux) ou sur la base de l’origine (appels d’urgence statiques ou dynamiques). Les appels entrants ne sont pas un problème, car l’appel ne peut provenir que d’une jonction associée au numéro. Toutefois, les appels sortants peuvent être dirigés vers n’importe quelle Appliance Cloud Connector dans un site (et par extension des jonctions RTC connectées à cette appliance Cloud Connector), ce qui peut entraîner des appels longue distance indésirables. Par ailleurs, les appels d’urgence ne sont pas transmis si le site RTC du Cloud Connector est étiré sur plusieurs centres de communications avec des codes de région différents ou des opérateurs.
  
## <a name="an-example"></a>Exemple

L’exemple suivant montre comment regrouper des jonctions sur des sites PSTN et comment affecter des utilisateurs aux sites. Pour Contoso Company, supposons les points suivants :
  
- Il y a quatre utilisateurs : 
    
  - Utilisateur A à Redmond WA (États-Unis)
    
  - Utilisateur B dans Bellevue WA (États-Unis)
    
  - Utilisateur C dans Centralia WA (États-Unis)
    
  - Utilisateur D à Portland ou (États-Unis)
    
- Le transporteur A fournit des numéros de téléphone et des jonctions dans :
    
  - Redmond (indicatif régional 425)
    
  - Bellevue (indicatif régional 425)
    
  - Centralia (indicatif régional 360)
    
- L’opérateur B fournit des numéros de téléphone et des jonctions dans :
    
  -  Portland (indicatif régional 503)
    
Étant donné que l’utilisateur A à Redmond (Centre de données A) et l’utilisateur B dans Bellevue (Centre de données B) sont dans Suburbs à côté des uns des autres et dans le même indicatif régional (425), le transporteur A doit pouvoir faire un appel d’urgence de l’utilisateur A à Redmond sur la jonction dans Bellevue. 
  
Par conséquent, les utilisateurs A et B, ainsi que les jonctions Cloud Connector pour Bellevue et Redmond, peuvent se trouver dans le même site RTC Cloud Connector, comme illustré dans le diagramme suivant. Les appels d’urgence des utilisateurs d’un bureau peuvent être acheminés vers les jonctions dans l’autre. Vous devez toutefois vérifier auprès de votre opérateur que cela fonctionnera.
  
![Procédure de configuration des sites RTC](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Envisagez également les exemples suivants :
  
- L’utilisateur C dans Centralia, dont le numéro est fourni par le transporteur A, est un lecteur de deux heures et un indicatif de zone différent (360), d’un autre opérateur A les utilisateurs dans l’indicatif de zone Bellevue et Redmond 425. 
    
    Par conséquent, même si un appel émane de l’opérateur A, il est possible que le logiciel de routage des appels de l’opérateur dans Centralia indicatif régional 360 puisse rejeter un appel d’urgence entrant provenant de l’utilisateur B dans Bellevue indicatif 425. Dans ce cas, il est essentiel que l’opérateur confirme que Cloud Connector et ses jonctions associées dans les sites RTC Centralia peuvent gérer les appels entre les distances et les codes de zone.
    
- Dans la société de Portland, l’utilisateur D utilise un nombre et une jonction fournis par l’opérateur B, de sorte qu’il est hautement improbable que le transporteur B effectue un appel d’urgence à partir d’un numéro de téléphone appartenant à l’opérateur A. Ainsi, l’utilisateur D et l’appliance Cloud Connector et les jonctions associées à Portland doivent se trouver sur un autre site RTC.
    

