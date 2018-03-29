---
title: Trunk MN dans Skype pour Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: 'Skype pour Business Server Voix Entreprise prend en charge le trunking n : n entre le serveur de médiation et de composants tels que les passerelles RTPC, contrôleurs de bordure session et IP-PBX.'
ms.openlocfilehash: 2f94bc0981a4fe1a171a02259db399b7cbaf6e48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mn-trunk-in-skype-for-business-server-2015"></a>Jonction M:N dans Skype Entreprise Server 2015
 
Skype pour Business Server Voix Entreprise prend en charge le trunking n : n entre le serveur de médiation et de composants tels que les passerelles RTPC, contrôleurs de bordure session et IP-PBX.
  
Skype pour Business Server prend en charge une plus grande souplesse dans la définition d’un tronc à des fins de routage d’appel à partir de versions précédentes. Une ligne est une association entre un serveur de médiation et d’un numéro de port d’écoute de logique avec une passerelle et un numéro de port d’écoute. Cela implique plusieurs choses : un serveur de médiation peut avoir plusieurs puits pour la même passerelle ; un serveur de médiation peut avoir plusieurs puits y différentes passerelles ; à l’inverse, une passerelle peut avoir plusieurs troncs à différents serveurs de médiation.
  
Vous devez toujours créer un tronc racine lorsque vous utilisez le Générateur de topologies pour enregistrées une passerelle à la topologie. Le nombre de passerelles capable de gérer un serveur de médiation donné dépend de la capacité de traitement du serveur pendant les heures de disponibilité de pointe. Si vous déployez un serveur de médiation sur le matériel qui dépasse la configuration minimale requise pour Skype pour Business Server, comme décrit dans [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), puis l’estimation du nombre d’appels non-bypass active un Serveur de médiation autonome peut gérer est d’environ 1000 appels. Lors du déploiement de la réunion de matériel ces spécifications, le serveur de médiation devrait effectuer le transcodage, mais continuer à acheminer les appels pour plusieurs passerelles même si les passerelles ne gèrent pas media ignore.
  
Lorsque vous définissez un itinéraire d’appel, vous spécifiez les trunks associés à cet itinéraire, mais que vous ne spécifiez pas les serveurs de médiation associés à cet itinéraire. Au lieu de cela, vous utilisez Générateur de topologies pour associer des puits avec les serveurs de médiation. En d’autres termes, le routage détermine le tronc à utiliser pour un appel et, par la suite, le serveur de médiation associé à cette jonction est envoyé à la signalisation pour cet appel.
  
Le serveur de médiation peut être déployé comme un pool ; ce pool peut être colocalisé avec un pool frontal, ou il peut être déployé comme un pool de ressources autonomes. Lorsqu’un serveur de médiation est colocalisé avec un pool frontal, la taille du pool peut être au plus 12 (limite de la taille du pool de Registrar). Ensemble, ces nouvelles capacités augmentent la fiabilité et la flexibilité de déploiement pour les serveurs de médiation, mais ils nécessitent des fonctionnalités associées dans les entités homologues suivantes :
  
- **Passerelle RTC.** Un Skype pour passerelle qualifié de serveur d’entreprise doit implémenter l’équilibrage de charge DNS, qui permet à une passerelle de réseau (RTPC) qualifié téléphonique commuté agir comme un équilibreur de charge d’un pool de serveurs de médiation et, par conséquent, les appels de l’équilibrage de charge sur le pool .
    
- **Contrôleur de bordure de session.** Pour un SIP trunk, l’entité de l’homologue est un contrôleur de bordure de Session (SBC) à un fournisseur de services de téléphonie. Dans le sens à partir du pool de serveur de médiation de la colonie d’abeilles simulée, le SBC peut recevoir des connexions à partir de n’importe quel serveur de médiation dans le pool. Dans la direction de la colonie d’abeilles simulée pour le pool, le trafic peut être envoyé à un serveur de médiation dans le pool. Une méthode de parvenir est via DNS équilibrage de charge, si pris en charge par le fournisseur de services et de la colonie d’abeilles simulée. Une alternative consiste à donner au fournisseur de services les adresses IP de tous les serveurs de médiation dans le pool, et le fournisseur de services met en service dans leur colonie d’abeilles simulée comme un SIP trunk distinct pour chaque serveur de médiation. Le fournisseur de services gère ensuite l’équilibrage de charge pour ses propres serveurs. Pas de tous les fournisseurs de services ou SBCs peuvent prendre en charge ces fonctionnalités. En outre, le fournisseur de services peut facturer un supplément pour cette fonctionnalité. En général, chaque SIP trunk à le SBC entraîne un abonnement mensuel.
    
- **IP-PBX.** Dans la direction à partir du pool de serveur de médiation à la fin de l’IP-PBX SIP, l’IP-PBX peut recevoir des connexions à partir de n’importe quel serveur de médiation dans le pool. Dans la direction de l’IP-PBX pour le pool, le trafic peut être envoyé à un serveur de médiation dans le pool. IP-PBX de la plupart des ne prennent pas en charge l’équilibrage de la charge DNS, nous vous recommandons que chaque connexion SIP directe défini à partir de l’IP-PBX pour chaque serveur de médiation dans le pool. L’IP-PBX gère ensuite son propre équilibrage en répartissant le trafic sur le groupe agrégé. L’hypothèse est que le groupe agrégé a un ensemble cohérent de règles de routage à l’IP-PBX. Si tel IP-PBX prend en charge ce concept de groupe trunk et comment il croise la redondance de le de IP-PBX propre et architecture de clustering doit être déterminée avant de déterminer si un cluster de serveur de médiation peut interagir correctement avec un PBX IP.
    
Un pool de serveur de médiation doit disposer d’une vue uniforme de la passerelle homologue avec lequel elle interagit. Cela signifie que tous les membres du pool accèdent à la même définition de passerelle homologue à partir du magasin de configurations et qu’ils ont tous autant de chances d’interagir avec elle pour les appels sortants. Par conséquent, il n’existe aucun moyen de segmenter le pool afin que certains serveurs de médiation communiquer avec uniquement certains homologues de passerelle pour les appels sortants. Si cette segmentation est nécessaire, un pool distinct des serveurs de médiation doit être utilisé. Ce serait le cas, par exemple, si les fonctionnalités associées dans les passerelles RTC, jonctions SIP ou systèmes IP-PBX pour interagir avec un pool n’étaient pas présentes (voir plus haut dans cette rubrique).
  
Une passerelle RTPC, IP-PBX ou homologue de jonction SIP peut router vers plusieurs serveurs de médiation ou les puits qui y aboutissent. Le nombre de passerelles qui contrôle l’un pool spécifique de serveurs de médiation dépend du nombre d’appels qui utilisent le contournement de média. Si un grand nombre d’appels utiliser le contournement de média, un serveur de médiation dans le pool peut gérer plus grand nombre d’appels, étant donné que le seul traitement de couche de signalisation est nécessaire. 
  

