---
title: Planification pour sites RTC, version Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Pour plus d’informations sur la planification de vos sites RTC dans le Cloud Connector, consultez cette rubrique pour en savoir plus sur le routage des appels, qui est efficace et rentable.
ms.openlocfilehash: 7afc5ac09e80edf6b1502e9d169aee77b3bd69b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287033"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Planification pour sites RTC, version Cloud Connector
 
Pour plus d’informations sur la planification de vos sites RTC dans le Cloud Connector, consultez cette rubrique pour en savoir plus sur le routage des appels, qui est efficace et rentable.
  
Cette rubrique décrit ce que vous devez savoir sur l’édition Cloud Connector et sur le routage des appels pour vous permettre de planifier les sites RTC de votre Cloud Connector. Un site RTC est une combinaison d’appareils de connexion Cloud, déployée au même emplacement et avec des passerelles RTC communes connectées. Cette rubrique vous explique comment configurer la topologie de votre site Cloud Connector pour vous assurer que vos sites Cloud Connector peuvent gérer le routage de trafic entrant et sortant de tous les utilisateurs attribués à un site de la façon la plus rentable et efficace possible. Pour plus d’informations sur le Cloud Connector et les avantages des sites RTC, consultez l’offre [pour Skype entreprise version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Acheminement des appels et sites RTC Cloud Connector

Les sites RTC Cloud est une construction de topologie créée pour éviter des tarifs inutiles vers des distances et des pays tiers et garantir que les appels d’urgence sortants sont routés vers le Trunk approprié. Pour vous assurer d’un acheminement des appels efficace et rentable, y compris des appels aux services d’urgence, vous devez planifier soigneusement vos sites RTC et la manière dont les utilisateurs sont affectés à chaque site. 
  
Dans le cadre de votre planification pour Cloud Connector, il est essentiel que vous indiquiez à vos opérateurs l’emplacement de vos bureaux et de vos utilisateurs et où les jonctions RTC de l’opérateur se terminent. Vous devez utiliser vos opérateurs pour déterminer la façon dont les appels d’urgence peuvent être routés, puis les utiliser pour définir des sites RTC Cloud Connector et affecter des utilisateurs aux sites appropriés. Par exemple, vous devrez vous assurer que les jonctions qui se terminent au centre de données où le site RTC est étiré sont configurées pour traiter l’acheminement entrant et sortant de tous les numéros affectés aux utilisateurs de ce site. 
  
Chaque appareil Cloud Connector peut être connecté à plusieurs passerelles IP, PBX IP ou contrôleurs de frontière de session (SBCs). Dans la mesure où les passerelles et PBX sont connectés à des Trunks d’Telco (Trunk ou SIP), les appareils de connexion Cloud sont logiquement connectés aux Trunks RTC pour les appels entrants et sortants. Avec Cloud Connector et la connectivité RTC sur site, vous obtenez la jonction et les numéros de téléphone associés de votre opérateur local. Si votre entreprise est une grande entreprise, vous aurez peut-être plus d’un opérateur, surtout si votre entreprise s’étend sur plus d’une ville, d’un état ou d’un pays. Étant donné que votre opérateur est propriétaire du numéro de téléphone, il est responsable du traitement des appels d’urgence.
  
Dans Skype entreprise Online, tous les appareils de connecteur Cloud d’un site le traitent de la même façon, et les appels sortants sont dirigés vers des appareils Cloud Connector sur le même site. Chaque Cloud Connector dans un site est inter-connecté au même ensemble de jonctions RTC (entièrement maillées). Dans la mesure où chaque utilisateur est associé à un site RTC dans le Cloud Connector, tous les appels sortants de cet utilisateur (normal ou d’urgence) seront attribués à l’un des appareils Cloud Connector sur le site RTC auquel l’utilisateur est associé. 
  
Cloud Connector effectue l’acheminement des appels vers ses passerelles IP jointes, IP-PBX, SBC ou jonctions RTC directes. Cloud Connector n’est pas encore capable d’acheminement dynamique vers une jonction basée sur la destination (pour l’acheminement à moindre coût) ou basée sur l’origine (appels d’urgence dynamique ou statique). Les appels entrants ne sont pas un problème étant donné que l’appel peut uniquement provenir d’une jonction associée au numéro. Toutefois, les appels sortants peuvent être dirigés vers n’importe quel appareil Cloud Connector dans un site (et par extension des Trunks RTC attachés à ce matériel de connecteur Cloud), ce qui peut entraîner des appels longue distance indésirables. De plus, les appels d’urgence ne sont pas passés par le biais du fait que le site RTC du Cloud Connector est étendu dans les centres de donnes avec différents indicatifs ou opérateurs.
  
## <a name="an-example"></a>Un exemple

L’exemple suivant montre comment grouper des Trunks vers des sites RTC et comment affecter des utilisateurs aux sites. Pour l’entreprise Contoso, supposez ce qui suit :
  
- Pour ces quatre utilisateurs :   
    
  - Utilisateur A à Redmond, Washington (É-U)
    
  - Utilisateur B à Bellevue, Washington (É-U)
    
  - Utilisateur C à Centralia, Washington (É-U)
    
  - Utilisateur D de Portland ou (États-Unis)
    
- Le transporteur A fournit des numéros de téléphone et des lignes en:
    
  - Redmond (indicatif régional 425)
    
  - Bellevue (indicatif régional 425)
    
  - Centralia (indicatif régional 360)
    
- Le transporteur B fournit des numéros de téléphone et des lignes de téléphone:
    
  -  Portland (indicatif régional 503)
    
Dans la mesure où l’utilisateur A à Redmond (Centre de données A) et l’utilisateur B dans Bellevue (Centre de données B) se trouvent dans banlieue parisienne en regard des uns des autres et dans le même code de zone (425), le transporteur A devrait être en mesure de passer un appel d’urgence de l’utilisateur A à Redmond sur le Trunk dans Bellevue. 
  
Par conséquent, les utilisateurs A et B et les Trunks de connecteur Cloud pour Bellevue et Redmond peuvent se trouver dans le même site PSTN du Cloud Connector, comme le montre le diagramme suivant. Les appels d’urgence des utilisateurs dans un bureau peuvent être acheminés vers les jonctions dans l’autre. Néanmoins, vous devez vérifier que votre opérateur fonctionne.
  
![Procédure de configuration de sites RTC](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considérez également les exemples suivants :
  
- L’utilisateur C à Centralia, dont le numéro est fourni par l’opérateur A,est à deux heures de route et a un indicatif régional différent (360), des autres utilisateurs de l’opérateur A avec l’indicatif régional 425 de Bellevue et Redmond.   
    
    Par conséquent, même si un appel provient du transporteur a, il est possible que le logiciel de routage des appels de l’opérateur dans Centralia 360 code de zone soit rejeté un appel d’urgence entrant provenant de l’utilisateur B dans Bellevue code de zone 425. Dans le cas présent, il est essentiel que l’opérateur confirme que le connecteur Cloud et ses lignes associées dans les sites RTC Centralia peuvent gérer les appels sur les distances et les indicatifs.
    
- Dans le cas contraire, l’utilisateur de Portland utilise un numéro et un Trunk fourni par l’opérateur B, de sorte qu’il est très improbable que le transporteur A un appel d’urgence à partir d’un numéro de téléphone possédé par le transporteur A. C’est pourquoi l’appliance D et l’appareil de connexion Cloud et les liaisons associées dans Portland doivent se trouver sur un site PSTN différent.
    

