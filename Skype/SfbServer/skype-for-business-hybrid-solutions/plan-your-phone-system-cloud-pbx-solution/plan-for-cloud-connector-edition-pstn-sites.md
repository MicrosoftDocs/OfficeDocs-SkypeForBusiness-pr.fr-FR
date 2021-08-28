---
title: Planification de l’édition Cloud Connecteur pour les sites PSTN
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lisez cette rubrique pour découvrir comment planifier vos sites RSTN Cloud Connector Edition afin de garantir un routage des appels efficace et rentable.
ms.openlocfilehash: 54f8ec9f89c6a3ef88b5ac8e70e9eebfd2968d2d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616330"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planification de l’édition Cloud Connecteur pour les sites PSTN

> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)
 
Lisez cette rubrique pour découvrir comment planifier vos sites RSTN Cloud Connector Edition afin de garantir un routage des appels efficace et rentable.
  
Cette rubrique décrit ce que vous devez savoir sur Cloud Connector Edition et le routage des appels afin de pouvoir planifier vos sites PSTN Cloud Connector. Un site PSTN est une combinaison d’appliances Cloud Connector, déployées au même emplacement et avec des passerelles PSTN communes qui leur sont connectées. Cette rubrique se concentre sur la façon de configurer votre topologie de site Cloud Connector pour vous assurer que vos sites Cloud Connector peuvent gérer le routage entrant et sortant pour tous les utilisateurs affectés à un site de la manière la plus rentable et la plus efficace possible. Pour plus d’informations sur Cloud Connector et les avantages des sites PSTN, n’oubliez pas de lire [Planifier Skype Entreprise Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sites RSTN Cloud Connector et routage des appels

Les sites PSTN Cloud Connector sont une construction de topologie créée pour éviter les dépenses longues et inter-pays inutiles, et pour s’assurer que les appels d’urgence sortants sont acheminés vers la liaison appropriée. Pour garantir un routage rentable et efficace des appels, y compris les appels aux services d’urgence, vous devez soigneusement planifier vos sites PSTN et la façon dont les utilisateurs sont affectés à chaque site. 
  
Dans le cadre de votre planification de Cloud Connector, il est essentiel que vous parliez à vos opérateurs de l’emplacement de vos bureaux et utilisateurs et de l’endroit où les connexions PSTN se terminent par l’opérateur. Vous devez travailler avec vos opérateurs pour déterminer comment les appels d’urgence peuvent être acheminés, puis utiliser ces informations pour définir des sites PSTN Cloud Connector et affecter des utilisateurs aux sites appropriés. Par exemple, vous devez vous assurer que les tronçons qui se terminent dans un centre de données où le site RSTN est étiré sont configurés pour gérer le routage entrant et sortant pour tous les numéros affectés aux utilisateurs de ce site. 
  
Chaque appliance Cloud Connector peut être connectée à plusieurs passerelles IP, PBX IP ou contrôleurs de frontière de session (SCS). Étant donné que les passerelles et les PBX sont connectés à des trunks telco (pri ou SIP), les appliances Cloud Connector sont connectées logiquement aux connexions PSTN pour les appels entrants et sortants. Avec Cloud Connector et la connectivité PSTN locale, vous obtenez la connexion et les numéros de téléphone associés auprès de votre opérateur local. Si votre entreprise est une grande entreprise, vous pouvez avoir plusieurs opérateurs, en particulier si votre entreprise s’étend sur plusieurs villes, états ou pays. Étant donné que votre opérateur est propriétaire du numéro de téléphone, il est responsable de la gestion des appels d’urgence.
  
Skype Entreprise Online traite toutes les appliances Cloud Connector d’un site de la même manière et route les appels sortants en rotation vers les appliances Cloud Connector dans le même site. Chaque Cloud Connector d’un site est connecté au même ensemble de connecteurs PSTN (entièrement maillage). Étant donné que chaque utilisateur est associé à un site RSTN Cloud Connector, tout appel sortant de cet utilisateur (normal ou d’urgence) est affecté à l’une des appliances Cloud Connector dans le site PSTN associé à l’utilisateur. 
  
Cloud Connector fait le routage d’appels statiques vers ses passerelles IP jointes, pbX IP, SCS ou ses branches PSTN directes. Cloud Connector n’est pas encore capable d’un routage dynamique vers une connexion basée sur la destination (pour le routage le moins coûteux) ou sur la base de l’origine (appels d’urgence statiques ou dynamiques). Les appels entrants ne sont pas un problème, car l’appel peut uniquement être issu d’une ligne associée au numéro. Toutefois, les appels sortants peuvent être appelés vers n’importe quelle appliance Cloud Connector d’un site (et par extension les branches PSTN attachées à cette appliance Cloud Connector), ce qui peut entraîner des appels longue distance indésirables. En outre, les appels d’urgence ne passeront pas si le site PSTN Cloud Connector est étiré dans les centres de données avec des indicatifs régionaux ou des opérateurs différents.
  
## <a name="an-example"></a>Exemple

L’exemple suivant montre comment grouper des trunks vers des sites PSTN et comment affecter des utilisateurs aux sites. Pour l’entreprise Contoso, supposez les hypothèses suivantes :
  
- Il y a quatre utilisateurs : 
    
  - Utilisateur A à Redmond WA (États-Unis)
    
  - Utilisateur B à Bellevue WA (États-Unis)
    
  - Utilisateur C dans Centralia WA (États-Unis)
    
  - Utilisateur D à Portland OR (États-Unis)
    
- L’opérateur A fournit des numéros de téléphone et des trunks dans :
    
  - Redmond (code de zone 425)
    
  - Bellevue (code de zone 425)
    
  - Centralia (code de zone 360)
    
- L’opérateur B fournit des numéros de téléphone et des trunks dans :
    
  -  Portland (code de zone 503)
    
Étant donné que l’utilisateur A à Redmond (Centre de données A) et l’utilisateur B à Bellevue (Centre de données B) sont en situation d’accès les uns à côté des autres et dans le même code de zone (425), l’opérateur A doit pouvoir prendre un appel d’urgence de l’utilisateur A à Redmond sur la ligne à Bellevue. 
  
Par conséquent, les utilisateurs A et B, ainsi que les trunks Cloud Connector pour Bellevue et Redmond, peuvent probablement se trouver sur le même site RSTN Cloud Connector, comme illustré dans le diagramme suivant. Les appels d’urgence des utilisateurs d’un bureau peuvent être acheminés vers des trunks dans l’autre. Toutefois, vous devez vérifier auprès de votre opérateur que cela fonctionne.
  
![Comment configurer des sites PSTN](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Prenons également les exemples suivants :
  
- L’utilisateur C de Centralia, dont le numéro est fourni par l’opérateur A, est à deux heures de route et dans un autre code de zone (360), des autres utilisateurs de l’opérateur A dans le code de zone Bellevue et Redmond 425. 
    
    Par conséquent, même si un appel provient de l’opérateur A, il est possible que le logiciel de routage des appels de l’opérateur dans l’code de zone Centralia 360 puisse rejeter un appel d’urgence entrant provenant de l’utilisateur B dans l’code de zone 425 de Bellevue. Dans ce cas, il est essentiel que l’opérateur confirme que Cloud Connector et ses branches associées dans les sites PSTN Centralia peuvent gérer les appels sur des distances et des indicatifs régionaux.
    
- L’utilisateur D de Portland utilise un numéro et une ligne fournis par l’opérateur B. Il est donc très peu probable que l’opérateur B prenne un appel d’urgence à partir d’un numéro de téléphone qui appartient à l’opérateur A. L’utilisateur D et l’appliance Cloud Connector et les branches associées à Portland devront donc se trouver dans un autre site PSTN.
