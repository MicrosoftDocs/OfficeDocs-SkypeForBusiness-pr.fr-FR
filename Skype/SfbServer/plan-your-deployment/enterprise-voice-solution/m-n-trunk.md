---
title: Jonction de MN dans Skype pour Business Server
ms.reviewer: ''
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
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: 'Skype pour Business Server Enterprise Voice prend en charge l’acheminement de m : n entre le serveur de médiation et des composants tels que les passerelles PSTN, les contrôleurs de frontière de session et IP-PBX.'
ms.openlocfilehash: d37233be20d8cf1a14faa3ca3abe1377127d0803
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892237"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>Jonction m : n dans Skype pour Business Server
 
Skype pour Business Server Enterprise Voice prend en charge l’acheminement de m : n entre le serveur de médiation et des composants tels que les passerelles PSTN, les contrôleurs de frontière de session et IP-PBX.
  
Skype pour Business Server prend en charge une plus grande souplesse dans la définition d’une jonction à des fins de routage appel à partir de versions précédentes. Un tronçon est une association entre un serveur de médiation et le numéro de port d’écoute logique avec une passerelle et un numéro de port d’écoute. Cela implique plusieurs tâches : un serveur de médiation peut avoir plusieurs jonctions vers la même passerelle ; un serveur de médiation peut avoir plusieurs jonctions à différentes passerelles ; Inversement, une passerelle peut avoir plusieurs jonctions à différents serveurs de médiation.
  
Vous devez toujours créer une jonction racine lorsque vous utilisez le Générateur de topologie pour enregistrées une passerelle à la topologie. Le nombre de passerelles capable de gérer un serveur de médiation donné dépend de la capacité de traitement du serveur pendant les heures de pointe occupé (e). Si vous déployez un serveur de médiation sur du matériel qui dépasse la configuration matérielle minimale requise pour Skype pour Business Server, comme indiqué dans la [configuration serveur requise pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), puis l’estimation du nombre d’appels sans contournement active un Serveur de médiation autonome peut gérer est d’environ 1000 appels. Lors du déploiement de la réunion de matériel ces spécifications, le serveur de médiation est prévu pour effectuer le transcodage, mais toujours acheminer les appels de plusieurs passerelles, même si les passerelles non compatibles le contournement de média.
  
Lorsque vous définissez un itinéraire d’appel, vous spécifiez les jonctions associées à cet itinéraire, mais vous ne spécifiez pas qui sont des serveurs de médiation associés à cet itinéraire. Au lieu de cela, vous utilisez le Générateur de topologie pour associer des jonctions avec les serveurs de médiation. En d’autres termes, routage détermine quels jonction à utiliser pour un appel et, par la suite, le serveur de médiation associé à ce tronçon est envoyé à la signalisation d’appel.
  
Le serveur de médiation peut être déployé en tant que pool ; ce pool peut être colocalisé avec un pool frontal, ou elle peut être déployé comme un pool autonome. Lorsqu’un serveur de médiation est colocalisé avec un pool frontal, la taille du pool peut être au plus 12 (la limite de la taille du pool de serveurs d’inscriptions). Ensemble, ces nouvelles capacités augmentent la fiabilité et la flexibilité de déploiement pour les serveurs de médiation, mais ils nécessitent des fonctionnalités associées dans les entités homologue suivantes :
  
- **Passerelle RTC.** Un Skype pour la passerelle Business Server complet doit implémenter l’équilibrage de charge DNS, ce qui permet une passerelle de réseau (PSTN) public commuté complet agir comme un équilibreur de charge pour un pool de serveurs de médiation et donc d’équilibrer les appels entre le pool .
    
- **Contrôleur de session en périphérie.** Pour une jonction SIP, l’entité homologue est un contrôleur de frontière de Session (SBC) à un fournisseur de services de téléphonie Internet. Dans le sens du pool de serveurs de médiation pour le contrôleur SBC, le contrôleur SBC peut recevoir des connexions à partir de n’importe quel serveur de médiation du pool. Dans le sens le contrôleur SBC vers le pool, le trafic peut être envoyé vers n’importe quel serveur de médiation du pool. Une méthode de parvenir consiste via l’équilibrage de charge DNS pris en charge par le fournisseur de services et SBC. Une alternative consiste à donner le fournisseur de services les adresses IP de tous les serveurs de médiation du pool et le fournisseur de services met en service dans leur SBC comme une jonction SIP distincte pour chaque serveur de médiation. Le fournisseur de services gère ensuite l’équilibrage de charge pour ses serveurs. Pas de tous les fournisseurs de services ou SBCs peuvent prendre en charge ces fonctionnalités. En outre, le fournisseur de services peut frais supplémentaires pour cette fonctionnalité. En règle générale, chaque jonction SIP pour le contrôleur SBC entraîne un abonnement mensuel.
    
- **IP-PBX.** Dans le sens du pool de serveurs de médiation à la fin de l’IP-PBX SIP, le système IP-PBX peut recevoir des connexions à partir de n’importe quel serveur de médiation du pool. Dans le sens de l’IP-PBX vers le pool, le trafic peut être envoyé vers n’importe quel serveur de médiation du pool. Étant donné que la plupart des systèmes PBX IP ne prennent pas en charge l’équilibrage de charge DNS, nous vous recommandons de qu’individuelles connexions SIP directes défini dans le système IP-PBX pour chaque serveur de médiation du pool. Le système IP-PBX gère ensuite son propre équilibrage en répartissant le trafic sur le groupe de jonction. Il est supposé que le groupe de jonction a un ensemble cohérent de règles de routage à l’IP-PBX. Si tel IP-PBX prend en charge ce concept de groupe de jonction et comment il croise la redondance de IP-PBX propre et architecture de clustering doit être déterminée avant de déterminer si un cluster de serveur de médiation peut interagir correctement avec un système IP-PBX.
    
Un pool de serveurs de médiation doit avoir un affichage de la passerelle de pair avec lequel elle interagit uniform. Cela signifie que tous les membres du pool accèdent à la même définition de passerelle homologue à partir du magasin de configurations et qu’ils ont tous autant de chances d’interagir avec elle pour les appels sortants. Par conséquent, il n’existe aucun moyen de segment du pool afin que certains serveurs de médiation communiquer avec certains homologues de passerelle pour les appels sortants. Si ce segmentation est nécessaire, un pool de serveurs de médiation distinct doit être utilisé. Ce serait le cas, par exemple, si les fonctionnalités associées dans les passerelles RTC, jonctions SIP ou systèmes IP-PBX pour interagir avec un pool n’étaient pas présentes (voir plus haut dans cette rubrique).
  
Une passerelle PSTN, IP-PBX ou homologue de jonction SIP peut acheminer sur plusieurs serveurs de médiation ou jonctions. Le nombre de passerelles un pool de serveurs de médiation particulier peut contrôler varie selon le nombre d’appels qui utilisent le contournement de média. Si un grand nombre d’appels utilisent le contournement de média, un serveur de médiation du pool peuvent gérer plus grand nombre d’appels, car seul traitement de couche de signalisation est nécessaire. 
  

