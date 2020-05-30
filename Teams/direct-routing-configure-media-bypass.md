---
title: Configurer le contournement de média avec un routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment configurer la dérivation multimédia avec le routage direct du système téléphonique pour Microsoft teams en faisant basculer tous les utilisateurs à la fois ou en implémentant une approche progressive (recommandé).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416894"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurer le contournement de média avec un routage direct

Avant de configurer la dérivation de médias avec le routage direct, assurez-vous d’avoir un [plan de lecture pour la dérivation de média avec le routage direct](direct-routing-plan-media-bypass.md).

Pour activer le contournement du contenu multimédia, les conditions suivantes doivent être remplies :

1.    Assurez-vous que le fournisseur de votre contrôleur de bordure de session (SBC) prend en charge la méthode de contournement du contenu multimédia et fournit des instructions sur la configuration du contournement sur la SBC. Reportez-vous à la page de certification pour en savoir plus sur les éléments SBCs, qui prennent en charge la contournement du support technique et des instructions.

2.    Vous devez activer la dérivation multimédia sur le Trunk en utilisant la commande suivante : **Set-CSOnlinePSTNGateway-identity <sbc_FQDN>-MediaBypass $true**.

3.    Vérifiez que les ports requis sont ouverts. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrer entre des Trunks non ignorés et des Trunks compatibles avec bypass

Vous pouvez basculer tous les utilisateurs à la fois ou vous pouvez implémenter une approche échelonnée (recommandé).

- **Basculer tous les utilisateurs en même temps.** Si toutes les conditions sont remplies, vous pouvez activer le mode contournement. Toutefois, tous vos utilisateurs de production seront basculés en même temps. Comme il se peut que vous rencontriez des problèmes au départ lorsque vous configurez des Trunks et des ports, il est possible que l’interface utilisateur de production soit affectée. 

- **Approche progressive. (Recommandé)**.  Créez une nouvelle Trunk pour la même SBC (avec un port différent), testez-la, puis modifiez la stratégie de routage de la voix en ligne pour les utilisateurs afin qu’ils pointent vers le nouveau Trunk. 

  Il s’agit de l’approche recommandée, car elle permet une transition plus fluide et une utilisation ininterrompue des utilisateurs. Cette approche nécessite une configuration de SBC, un nouveau nom de domaine complet et une configuration du pare-feu. Remarque vous devrez vous assurer que votre certificat prend en charge les deux Trunks. Dans SAN, vous devez avoir deux noms (**sbc1.contoso.com** et **sbc2.contoso.com**) ou avoir un certificat générique.

![Migrer entre des Trunks non ignorés et des Trunks compatibles avec le contournement du réseau.](media/direct-routing-media-bypass-8.png)

Pour obtenir des instructions sur la façon de configurer les Trunks et de procéder à la migration, consultez la documentation de votre fournisseur de SBC :

- [Documentation de déploiement AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation relative au déploiement d’Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation sur le déploiement des communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation sur le déploiement de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Pour obtenir la liste des contrôleurs de frontière de session (SBCs) certifiés pour le routage direct, voir [liste des contrôleurs de session des bordures certifiés pour le routage direct](direct-routing-border-controllers.md).



## <a name="related-topics"></a>Voir aussi

[Envisager une dérivation de média avec le routage direct](direct-routing-plan-media-bypass.md)



