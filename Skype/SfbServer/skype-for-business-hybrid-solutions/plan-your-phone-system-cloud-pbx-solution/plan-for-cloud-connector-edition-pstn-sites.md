---
title: Planification pour sites RTC, version Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lisez cette rubrique pour obtenir des informations sur la planification de vos sites de nuage lien édition RTPC pour garantir le routage des appels efficace et économique.
ms.openlocfilehash: 70e5806ac6187d23b725f98ef288acaca7c03a54
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planification pour sites RTC, version Cloud Connector
 
Lisez cette rubrique pour obtenir des informations sur la planification de vos sites de nuage lien édition RTPC pour garantir le routage des appels efficace et économique.
  
Cette rubrique décrit ce que vous devez savoir sur le nuage lien édition et appeler le routage de sorte que vous pouvez planifier vos sites de nuage connecteur PSTN. Un site RTC est une combinaison de matériel de connecteur de nuage, déployé au même emplacement et avec les passerelles RTPC communs connectés. Cette rubrique se concentre sur la manière de configurer votre topologie de site connecteur du nuage pour vous assurer que vos sites de connecteur de nuage peuvent gérer le routage entrant et sortant pour tous les utilisateurs affectés à un site de la plupart des coûts efficace et optimale. Pour plus d’informations sur le connecteur du nuage et les avantages des sites de RTPC, veillez à lire [planifier Skype pour connecteur de Cloud Business Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Acheminement des appels et sites RTC Cloud Connector

Sites de connecteur PSTN nuage sont une construction de la topologie créée afin d’éviter d’inutile longue distance et tarifs entre pays et afin de garantir que les appels d’urgence sortants sont routés vers le tronc approprié. Pour vous assurer d’un acheminement des appels efficace et rentable, y compris des appels aux services d’urgence, vous devez planifier soigneusement vos sites RTC et la manière dont les utilisateurs sont affectés à chaque site. 
  
Dans le cadre de votre planification pour Cloud Connector, il est essentiel que vous indiquiez à vos opérateurs l’emplacement de vos bureaux et de vos utilisateurs et où les jonctions RTC de l’opérateur se terminent. Vous devez travailler avec vos opérateurs pour déterminer comment le secours appelle peut être acheminés et ensuite utiliser ces informations pour définir les sites de nuage connecteur RTPC et d’affecter des utilisateurs aux sites appropriés. Par exemple, vous devrez vous assurer que les jonctions qui se terminent au centre de données où le site RTC est étiré sont configurées pour traiter l’acheminement entrant et sortant de tous les numéros affectés aux utilisateurs de ce site. 
  
La solution matérielle-logicielle chaque connecteur de nuage peut être connecté à plusieurs passerelles IP, les PBX IP ou contrôleurs de bordure de Session (SBCs). Les passerelles et les PBX est connecté à puits de télécommunications (puits PRI ou SIP), appliances de connecteur de nuage sont logiquement connectés à puits RTPC pour les appels entrants et sortants. Avec Cloud Connector et la connectivité RTC sur site, vous obtenez la jonction et les numéros de téléphone associés de votre opérateur local. Si votre entreprise est une grande entreprise, vous aurez peut-être plus d’un opérateur, surtout si votre entreprise s’étend sur plus d’une ville, d’un état ou d’un pays. Étant donné que votre opérateur est propriétaire du numéro de téléphone, il est responsable du traitement des appels d’urgence.
  
Skype pour entreprise en ligne traite de manière égale tous les matériels de connecteur du Cloud dans un site et de route les appels sortants sur une base cyclique aux appliances de connecteur du Cloud dans le même site. Chaque Cloud Connector dans un site est inter-connecté au même ensemble de jonctions RTC (entièrement maillées). Étant donné que chaque utilisateur est associé à un site de nuage connecteur PSTN, tout appel sortant à partir de cet utilisateur (normal ou d’urgence) recevront à une de ces solutions de nuage connecteur dans le site RTPC qui est associé à l’utilisateur. 
  
Cloud Connector effectue l’acheminement des appels vers ses passerelles IP jointes, IP-PBX, SBC ou jonctions RTC directes. Cloud Connector n’est pas encore capable d’acheminement dynamique vers une jonction basée sur la destination (pour l’acheminement à moindre coût) ou basée sur l’origine (appels d’urgence dynamique ou statique). Les appels entrants ne sont pas un problème étant donné que l’appel peut uniquement provenir d’une jonction associée au numéro. Appels sortants, cependant, peuvent atteindre n’importe quel matériel de connecteur du Cloud dans un site (et par extension les trunks RTPC reliés au commutateur connecteur de Cloud) qui peut entraîner des appels longue distance indésirables. En outre, les appels d’urgence ne va pas aller en si le site de nuage connecteur PSTN est étiré sur les centres de données avec différents codes de zone ou les transporteurs.
  
## <a name="an-example"></a>Un exemple

L’exemple suivant montre comment regrouper les puits qui y aboutissent à des sites RTPC et comment assigner des utilisateurs aux sites. Pour l’entreprise Contoso, supposez ce qui suit :
  
- Pour ces quatre utilisateurs :   
    
  - Utilisateur A à Redmond, Washington (É-U)
    
  - Utilisateur B à Bellevue, Washington (É-U)
    
  - Utilisateur C à Centralia, Washington (É-U)
    
  - Utilisateur D de Portland, OR (États-Unis)
    
- TRANSPORTEUR A fournit des numéros de téléphone et les puits y dans :
    
  - Redmond (indicatif régional 425)
    
  - Bellevue (indicatif régional 425)
    
  - Centralia (indicatif régional 360)
    
- Transporteur B fournit les numéros de téléphone et les puits y dans :
    
  -  Portland (indicatif régional 503)
    
Étant donné que l’utilisateur A à Redmond et l’utilisateur B à Bellevue sont dans des banlieues proches l’un de l’autre et ont le même indicateur régional (425), l’opérateur A devrait pouvoir prendre un appel d’urgence de l’utilisateur A à Redmond sur la jonction à Bellevue.   
  
Par conséquent, les utilisateurs A et B et les puits de connecteur de nuage pour Bellevue et Redmond, peuvent probablement être dans le même site RTPC comme illustré dans le diagramme suivant. Les appels d’urgence des utilisateurs dans un bureau peuvent être acheminés vers les jonctions dans l’autre. Toutefois, vérifiez auprès de votre porteuse pour que cela fonctionne.
  
![Procédure de configuration de sites RTC](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considérez également les exemples suivants :
  
- L’utilisateur C à Centralia, dont le numéro est fourni par l’opérateur A,est à deux heures de route et a un indicatif régional différent (360), des autres utilisateurs de l’opérateur A avec l’indicatif régional 425 de Bellevue et Redmond.   
    
    Par conséquent, même si un appel est en provenance de transporteur A, il est possible qu’appel de l’opérateur le logiciel de routage dans le code de zone Centralia 360 peut refuser d’urgence entrante appel provenant de l’utilisateur B dans le code de zone Bellevue 425. Dans ce cas, il est essentiel que le transporteur confirmer que connecteur du nuage et ses puits associées dans les sites Centralia RTPC peuvent gérer les appels entre les distances et les codes de zone.
    
- Utilisateur D à Portland utilise un numéro et trunk fourni par le transporteur B, il est hautement improbable que B de transporteur aura un appel d’urgence à partir d’un numéro de téléphone qui est détenu par le transporteur A. Afin que l’utilisateur D appliance de connecteur du nuage et de troncs associés à Portland doivent se trouver dans un autre site RTPC.
    

