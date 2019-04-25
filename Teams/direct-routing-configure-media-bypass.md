---
title: Configurer le contournement de média avec un routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lisez cette rubrique pour savoir comment configurer le contournement de média avec le routage d’un système téléphonique Direct.
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232693"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurer le contournement de média avec un routage direct

Avant de configurer le contournement de média avec le routage Direct, veillez à ce que vous avez lu [Plan pour le média de contournement de média avec le routage Direct](direct-routing-plan-media-bypass.md).

Pour activer le contournement de média, les conditions suivantes doivent être remplies :

1.  Assurez-vous que votre fournisseur de contrôleur de Session en périphérie (SBC) de choix prend en charge le contournement de média et fournit des instructions sur la configuration de contournement de média sur le contrôleur SBC. Reportez-vous à la page de certification pour en savoir plus sur SBC, qui le support celles contournement de média, et pour obtenir des instructions.

2.  Vous devez activer le contournement de média sur la jonction à l’aide de la commande suivante : **Set-CSOnlinePSTNGateway-Identity <sbc_FQDN> - MediaBypass $true**.

3.  Assurez-vous que les ports requis sont ouverts. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migration de jonctions non contourné vers jonctions prenant en charge contournement de média

Vous pouvez changer de tous les utilisateurs à la fois, ou vous pouvez implémenter une approche progressive (recommandé).

- **Changer de tous les utilisateurs à la fois.** Si toutes les conditions sont remplies, vous pouvez activer le mode de contournement de média. Toutefois, tous les utilisateurs de production bascule en même temps. Étant donné que vous rencontriez certains problèmes à l’origine lorsque vous configurez des jonctions et des ports, votre expérience utilisateur de production peut être affectée. 

- Approche **en phase. (Recommandé)**.  Créer une nouvelle jonction pour le même SBC (avec un autre port), tester et modifier la stratégie de routage voix en ligne pour les utilisateurs afin de pointer vers la nouvelle jonction. 

  Il s’agit de l’approche recommandée car elle permet une transition plus fluide et l’expérience utilisateur sans interruption. Cette approche nécessite la configuration du contrôleur SBC, un nouveau nom de domaine complet et la configuration du pare-feu. Notez que vous devez vous assurer que votre certificat prend en charge les jonctions. SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou dispose d’un certificat générique.

![Migration de jonctions non contourné vers jonctions prenant en charge contournement de média)](media/direct-routing-media-bypass-8.png)

Pour obtenir des instructions sur la façon de configurer les jonctions et effectuer la migration, consultez la documentation de votre fournisseur SBC :

- AudioCodes
- Ruban
- NOTE-Systems (AnyNode)    

Pour obtenir la liste de contrôleurs de frontière de Session (SBC) certifié pour le routage Direct, voir [liste de Session Broder contrôleurs certifiés pour le routage Direct](direct-routing-border-controllers.md).



## <a name="see-also"></a>Voir aussi

[Planifier le contournement de média avec le routage Direct](direct-routing-plan-media-bypass.md)



