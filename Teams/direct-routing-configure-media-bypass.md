---
title: Configurer le contournement de média avec un routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment configurer la dérivation média avec Système téléphonique routage direct pour Microsoft Teams en changeant tous les utilisateurs en une fois ou en implémentant une approche progressive (recommandé).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0f0ad9d25157058c048b0f12cf72b3755e65e11
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728683"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurer le contournement de média avec un routage direct

Avant de configurer la dérivation média avec le routage direct, veillez à lire le plan de dérivation [média avec le routage direct.](direct-routing-plan-media-bypass.md)

Pour activer la dérivation média, les conditions suivantes doivent être remplies :

1.    Assurez-vous que le fournisseur de votre choix de contrôleur de session border Controller (SBC) prend en charge la dérivation média et fournit des instructions sur la configuration de la dérivation sur le SBC. Reportez-vous à la page de certification pour en savoir plus sur les SBCs, lesquels supportent la dérivation média, et pour obtenir des instructions.

2.    Vous devez activer la dérivation média sur la ligne à l’aide de la commande suivante : **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**

3.    Assurez-vous que les ports requis sont ouverts. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrer des ligne sans contournement vers des ligne activées par dérivation

Vous pouvez changer tous les utilisateurs en une fois ou implémenter une approche progressive (recommandé).

- **Basculez tous les utilisateurs en une fois.** Si toutes les conditions sont remplies, vous pouvez activer le mode contournement. Toutefois, tous vos utilisateurs de production seront basculés en même temps. Comme vous risquez de faire face à des problèmes initialement lors de la configuration de ports et de ligne, votre expérience utilisateur en production peut être affectée. 

- **Approche progressive. (Recommandé).**  Créez une ligne pour le même port SBC (avec un autre port), testez-la et modifiez la stratégie de routage voix en ligne pour que les utilisateurs pointent vers la nouvelle ligne. 

  Il s’agit de l’approche recommandée, car elle permet une transition plus fluide et une expérience utilisateur ininterrompue. Cette approche nécessite la configuration du SBC, d’un nouveau nom de nom de domaine complet (FQDN) et de la configuration du pare-feu. Notez que vous devez vous assurer que votre certificat prend en charge les deux ligne. En san san, vous devez avoir deux noms **(sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.

![Migrer des ligne sans contournement vers des ligne activées par dérivation).](media/direct-routing-media-bypass-8.png)

Pour obtenir des instructions sur la configuration des ligne et l’étape de migration, consultez la documentation de votre fournisseur SBC :

- [Documentation sur le déploiement de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation sur le déploiement d’Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation de déploiement de Communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation sur le déploiement des systèmes TE (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Pour obtenir la liste des contrôleurs de session en bordure certifiés pour le routage direct, consultez la liste des contrôleurs de session Broder certifiés pour le [routage direct.](direct-routing-border-controllers.md)



## <a name="related-topics"></a>Sujets associés

[Planifier la dérivation média avec le routage direct](direct-routing-plan-media-bypass.md)



