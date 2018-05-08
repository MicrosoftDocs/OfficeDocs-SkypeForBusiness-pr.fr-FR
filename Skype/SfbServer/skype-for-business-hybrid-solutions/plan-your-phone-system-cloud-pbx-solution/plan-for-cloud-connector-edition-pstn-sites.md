---
title: Planification pour sites RTC, version Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lisez cette rubrique pour savoir comment planifier vos sites nuage connecteur Edition PSTN pour garantir le routage des appels efficace et économique.
ms.openlocfilehash: f9aaec14c0a3a13d38e579f3803bbe4216811741
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planification pour sites RTC, version Cloud Connector
 
Lisez cette rubrique pour savoir comment planifier vos sites nuage connecteur Edition PSTN pour garantir le routage des appels efficace et économique.
  
Cette rubrique décrit ce que vous devez savoir à propos de nuage connecteur Edition et le routage de sorte que vous pouvez planifier vos sites de nuage connecteur PSTN d’appel. Un site RTC est une combinaison de matériel de nuage connecteur, déployé au même emplacement et avec les passerelles PSTN courantes connectés. Cette rubrique se concentre sur la façon de configurer votre topologie de sites dans le nuage connecteur pour vous assurer que vos sites nuage connecteur peuvent gérer le routage entrant et sortant pour tous les utilisateurs affectés à un site dans la plupart coût moyen efficace possible. Pour plus d’informations sur le nuage connecteur et les avantages des sites PSTN, veillez à lire [planifier Skype pour l’édition de connecteur Business Cloud](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Acheminement des appels et sites RTC Cloud Connector

Nuage connecteur PSTN sites sont une construction de la topologie créée afin d’éviter inutile longue distance et tarifs entre pays et pour s’assurer que les appels d’urgence sortants sont routés vers la jonction appropriée. Pour vous assurer d’un acheminement des appels efficace et rentable, y compris des appels aux services d’urgence, vous devez planifier soigneusement vos sites RTC et la manière dont les utilisateurs sont affectés à chaque site. 
  
Dans le cadre de votre planification pour Cloud Connector, il est essentiel que vous indiquiez à vos opérateurs l’emplacement de vos bureaux et de vos utilisateurs et où les jonctions RTC de l’opérateur se terminent. Vous avez besoin travailler avec vos opérateurs afin de déterminer comment emergency appelle peuvent être acheminés et ensuite utiliser ces informations pour définir des sites de nuage connecteur PSTN et affecter des utilisateurs aux sites appropriés. Par exemple, vous devrez vous assurer que les jonctions qui se terminent au centre de données où le site RTC est étiré sont configurées pour traiter l’acheminement entrant et sortant de tous les numéros affectés aux utilisateurs de ce site. 
  
Chaque application de nuage connecteur peut être connectée à plusieurs passerelles IP, PBX IP ou contrôleurs de frontière de Session (SBC). Étant donné que les passerelles et PBX est connectés à jonctions télécommunications (PRI ou SIP jonctions), appliances nuage connecteur sont logiquement connectés à jonctions PSTN pour les appels entrants et sortants. Avec Cloud Connector et la connectivité RTC sur site, vous obtenez la jonction et les numéros de téléphone associés de votre opérateur local. Si votre entreprise est une grande entreprise, vous aurez peut-être plus d’un opérateur, surtout si votre entreprise s’étend sur plus d’une ville, d’un état ou d’un pays. Étant donné que votre opérateur est propriétaire du numéro de téléphone, il est responsable du traitement des appels d’urgence.
  
Skype pour Business Online traite tous les appareils de nuage connecteur dans un site de manière égale et route les appels sortants par rotation aux solutions de nuage connecteur dans le même site. Chaque Cloud Connector dans un site est inter-connecté au même ensemble de jonctions RTC (entièrement maillées). Étant donné que chaque utilisateur est associé à un site dans le nuage connecteur RTC, tout appel à partir de cet utilisateur (normal ou d’urgence) sera attribué à l’une des applications dans le nuage connecteur dans le site PSTN qui est associé à l’utilisateur. 
  
Cloud Connector effectue l’acheminement des appels vers ses passerelles IP jointes, IP-PBX, SBC ou jonctions RTC directes. Cloud Connector n’est pas encore capable d’acheminement dynamique vers une jonction basée sur la destination (pour l’acheminement à moindre coût) ou basée sur l’origine (appels d’urgence dynamique ou statique). Les appels entrants ne sont pas un problème étant donné que l’appel peut uniquement provenir d’une jonction associée au numéro. Les appels sortants, toutefois, pouvant accéder à n’importe quel appareil nuage connecteur dans un site (et par extension les jonctions PSTN connectées à ce connecteur de nuage) qui peut entraîner des appels longue distance indésirables. En outre, les appels d’urgence pas passeront si le site sur le nuage connecteur PSTN est étiré sur les centres de données avec différents codes de zone ou les opérateurs.
  
## <a name="an-example"></a>Un exemple

L’exemple suivant montre comment grouper les jonctions aux sites PSTN et comment affecter des utilisateurs aux sites. Pour l’entreprise Contoso, supposez ce qui suit :
  
- Pour ces quatre utilisateurs :   
    
  - Utilisateur A à Redmond, Washington (É-U)
    
  - Utilisateur B à Bellevue, Washington (É-U)
    
  - Utilisateur C à Centralia, Washington (É-U)
    
  - Utilisateur D dans Portland OR (États-Unis)
    
- Opérateur A fournit des numéros de téléphone et des jonctions dans :
    
  - Redmond (indicatif régional 425)
    
  - Bellevue (indicatif régional 425)
    
  - Centralia (indicatif régional 360)
    
- Opérateur B fournit des numéros de téléphone et des jonctions dans :
    
  -  Portland (indicatif régional 503)
    
Étant donné que l’utilisateur A à Redmond et l’utilisateur B à Bellevue sont dans des banlieues proches l’un de l’autre et ont le même indicateur régional (425), l’opérateur A devrait pouvoir prendre un appel d’urgence de l’utilisateur A à Redmond sur la jonction à Bellevue.   
  
Par conséquent, les utilisateurs A et B et les jonctions nuage connecteur pour Bellevue et Redmond, peuvent sera probablement dans le même site PSTN comme indiqué dans le diagramme suivant. Les appels d’urgence des utilisateurs dans un bureau peuvent être acheminés vers les jonctions dans l’autre. Toutefois, vérifiez auprès de votre opérateur que cela fonctionne.
  
![Procédure de configuration de sites RTC](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considérez également les exemples suivants :
  
- L’utilisateur C à Centralia, dont le numéro est fourni par l’opérateur A,est à deux heures de route et a un indicatif régional différent (360), des autres utilisateurs de l’opérateur A avec l’indicatif régional 425 de Bellevue et Redmond.   
    
    Par conséquent, même si l’opérateur A proviennent d’un appel, il est possible qu’appel de l’opérateur logiciel de routage dans le code de zone Centralia 360 peut rejeter d’urgence entrante appel provenant de l’utilisateur B dans Bellevue indicatif 425. Dans ce cas, il est essentiel que l’opérateur confirmer que nuage connecteur et son jonctions associées dans les sites Centralia PSTN peuvent gérer les appels entre les distances et les codes de zone.
    
- Utilisateur D Portland utilise un numéro et jonction fournie par l’opérateur B, il est très peu probable que B opérateur prendra un appel d’urgence à partir d’un numéro de téléphone qui détenue par l’opérateur A. Afin que l’utilisateur D et l’appliance nuage connecteur et jonctions associées à Portland doivent se trouver dans un autre site PSTN.
    

