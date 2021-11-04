---
title: MN trunk in Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
description: Skype Entreprise Server Voix Entreprise prend en charge la trunking M:N entre le serveur de médiation et des composants tels que les passerelles PSTN, les contrôleurs de frontière de session et IP-PBX.
ms.openlocfilehash: 28f5d7e9aae5406f54104e3411ecec6ba65ab7f4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770122"
---
# <a name="mn-trunk-in-skype-for-business-server"></a>M:N trunk in Skype Entreprise Server
 
Skype Entreprise Server Voix Entreprise prend en charge la trunking M:N entre le serveur de médiation et des composants tels que les passerelles PSTN, les contrôleurs de frontière de session et IP-PBX.
  
Skype Entreprise Server prend en charge une plus grande flexibilité dans la définition d’une ligne à des fins de routage des appels par rapport aux versions précédentes. Une trunk est une association logique entre un serveur de médiation et un numéro de port d’écoute avec une passerelle et un numéro de port d’écoute. Cela implique plusieurs choses : un serveur de médiation peut avoir plusieurs branches vers la même passerelle ; un serveur de médiation peut avoir plusieurs branches vers différentes passerelles ; inversement, une passerelle peut avoir plusieurs branches vers différents serveurs de médiation.
  
Vous devez toujours créer une troncaire racine chaque fois que vous utilisez le Générateur de topologie pour ajouter une passerelle à la topologie. Le nombre de passerelles qu’un serveur de médiation donné peut gérer dépend de la capacité de traitement du serveur pendant les heures de pointe. Si vous déployez un serveur de médiation sur du matériel qui dépasse la configuration matérielle minimale requise pour Skype Entreprise Server, comme décrit dans La configuration requise pour le serveur pour [Skype Entreprise Server 2015,](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)l’estimation du nombre d’appels actifs non contournement qu’un serveur de médiation autonome peut gérer est d’environ 1 000 appels. Lorsqu’il est déployé sur du matériel qui doit répondre à ces spécifications, le serveur de médiation est censé effectuer le transcodage, mais continue d’router les appels pour plusieurs passerelles, même si les passerelles ne la prise en charge du contournement de média.
  
Lors de la définition d’un itinéraire d’appels, vous spécifiez les liaisons associées à cet itinéraire, mais vous ne spécifiez pas les serveurs de médiation associés à cet itinéraire. Au lieu de cela, vous utilisez le Générateur de topologie pour associer des trunks à des serveurs de médiation. En d’autres termes, le routage détermine la trunk à utiliser pour un appel et, par la suite, le serveur de médiation associé à cette trunk est envoyé la signalisation pour cet appel.
  
Le serveur de médiation peut être déployé en tant que pool . Ce pool peut être cocisé avec un pool frontal, ou il peut être déployé en tant que pool autonome. Lorsqu’un serveur de médiation est coqueté avec un pool frontal, la taille du pool peut être au maximum 12 (limite de la taille du pool de serveurs d’inscriptions). Ensemble, ces nouvelles fonctionnalités augmentent la fiabilité et la flexibilité de déploiement des serveurs de médiation, mais elles nécessitent des fonctionnalités associées dans les entités homologues suivantes :
  
- **Passerelle PSTN.** Une passerelle Skype Entreprise Server qualifiée doit implémenter l’équilibrage de charge DNS, ce qui permet à une passerelle de réseau téléphonique commuté (PSTN) qualifiée d’agir en tant qu’équilibreur de charge pour un pool de serveurs de médiation, et par conséquent d’équilibrer la charge des appels dans le pool.
    
- **Contrôleur de frontière de session.** Pour une connexion SIP, l’entité homologue est un contrôleur SBC (Session Border Controller) chez un fournisseur de services de téléphonie Internet. Dans le sens entre le pool de serveurs de médiation et le SBC, le SBC peut recevoir des connexions à partir de n’importe quel serveur de médiation du pool. Dans le sens entre le contrôleur SBC et le pool, le trafic peut être envoyé à n’importe quel serveur de médiation du pool. Une méthode pour y parvenir consiste à équilibrer la charge DNS, si elle est prise en charge par le fournisseur de services et le SBC. Une autre solution consiste à fournir au fournisseur de services les adresses IP de tous les serveurs de médiation du pool, et le fournisseur de services les met en service dans leur SBC comme une ligne SIP distincte pour chaque serveur de médiation. Le fournisseur de services gère ensuite l’équilibrage de charge pour ses propres serveurs. Tous les fournisseurs de services ou SCS ne peuvent pas prendre en charge ces fonctionnalités. En outre, le fournisseur de services peut facturer des frais supplémentaires pour cette fonctionnalité. En règle générale, chaque branche SIP vers le SBC implique des frais mensuels.
    
- **IP-PBX.** Dans le sens entre le pool de serveurs de médiation et la terminaison SIP IP-PBX, le SYSTÈME IP-PBX peut recevoir des connexions à partir de n’importe quel serveur de médiation du pool. Dans le sens du PBX IP vers le pool, le trafic peut être envoyé à n’importe quel serveur de médiation du pool. Étant donné que la plupart des IP-PBXs ne prisent pas en charge l’équilibrage de charge DNS, nous vous recommandons de définir des connexions SIP directes individuelles à partir du SYSTÈME IP-PBX vers chaque serveur de médiation du pool. Le système IP-PBX gère ensuite son propre équilibrage de charge en répartissant le trafic dans le groupe de jonctions. Le groupe de jonctions est supposé avoir un ensemble cohérent de règles de routage sur le système IP-PBX. Vous devez déterminer si un SYSTÈME IP-PBX particulier prend en charge ce concept de groupe de trunks et comment il se coupe avec la redondance et l’architecture de clustering de l’IP-PBX avant de pouvoir déterminer si un cluster de serveur de médiation peut interagir correctement avec un IP-PBX.
    
Un pool de serveurs de médiation doit avoir une vue uniforme de la passerelle homologue avec laquelle il interagit. Cela signifie que tous les membres du pool accèdent à la même définition de passerelle homologue à partir du magasin de configurations et qu’ils ont tous autant de chances d’interagir avec elle pour les appels sortants. Par conséquent, il n’existe aucun moyen de segmenter le pool afin que certains serveurs de médiation communiquent uniquement avec certains homologues de passerelle pour les appels sortants. Si une telle segmentation est nécessaire, un pool distinct de serveurs de médiation doit être utilisé. Ce serait le cas, par exemple, si les fonctionnalités associées dans les passerelles PSTN, jonctions SIP ou systèmes IP-PBX pour interagir avec un pool n’étaient pas présentes (voir plus haut dans cette rubrique).
  
Une passerelle PSTN, un système IP-PBX ou un homologue de trunk SIP particulier peut être acheminé vers plusieurs serveurs de médiation ou plusieurs trunks. Le nombre de passerelles qu’un pool particulier de serveurs de médiation peut contrôler dépend du nombre d’appels qui utilisent le contournement de média. Si un grand nombre d’appels utilisent le contournement de média, un serveur de médiation dans le pool peut gérer beaucoup plus d’appels, car seul le traitement de couche de signalisation est nécessaire. 
  

