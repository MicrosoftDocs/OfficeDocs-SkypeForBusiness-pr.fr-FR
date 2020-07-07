---
title: Application de discussion de Microsoft teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Découvrez comment configurer l’application de discussion de Microsoft teams à partir d’un point de vue ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043009"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Application de discussion de Microsoft teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

L’application de notification de l’équipe de discussion dans teams fournit une communication instantanée et vocale pour votre équipe et sera bientôt disponible en préversion publique sur Android. Le Guide d’appel permet aux utilisateurs de communiquer avec leur équipe en utilisant les mêmes canaux sous-jacents dont ils sont membres. Seuls les utilisateurs qui se connectent à la fonctionnalité de conversation dans un canal deviennent des participants et pourront communiquer entre eux à l’aide de la fonctionnalité de communication d’une personne à la fois.

En équipe, vous pouvez à tout moment communiquer en toute sécurité avec une expérience PTT familière sans avoir besoin de transporter des radios en vrac, et de se familiariser avec la connectivité Internet WiFi ou mobile.

## <a name="getting-started"></a>Prise en main

### <a name="deploying-walkie-talkie"></a>Déploiement de l’étape de discussion

Dans le cadre de la préversion publique, l’étape de conversation n’est pas préinstallée. Pour activer cette fonctionnalité pour les utilisateurs de votre organisation, vous devez ajouter le propos de l’outil de [configuration de l’application](teams-app-setup-policies.md)   affecté aux utilisateurs dans le centre d' [administration teams](https://admin.teams.microsoft.com/).

Dès qu’il est activé, vous pouvez désormais accéder à la discussion sur l’application Android dans les 48 heures.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Ajouter un contact de votre liste d’applications

Dans le centre d’administration de Microsoft Teams, sous stratégies de configuration des **applications teams**  >  **Setup policies**, vous devez **On**activer l' **épinglage** pour l’utilisateur. Dans la section applications épinglées, cliquez sur **+ Ajouter des applications**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Affiche la section applications épinglées et le bouton Ajouter des applications à sélectionner.":::

Dans le volet **Ajouter des applications épinglées** qui s’affiche à droite, utilisez la zone de **recherche** pour rechercher un contact. Lorsque vous disposez d’un résultat de recherche, cliquez sur le bouton **Ajouter** à droite du nom pour l’ajouter à votre liste.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Affiche la barre latérale de l’option Ajouter des applications épinglées avec les résultats de la recherche dans le volet de recherche et l’application de présentation de l’aide du bouton Ajouter.":::

L’application de discussion à l’aide de l’application doit maintenant apparaître dans la liste des applications épinglées et être disponible lorsque vous cliquez sur le bouton **Enregistrer** .

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Affiche la liste des applications épinglées avec l’application de conversation de discussion ajoutée et le bouton Enregistrer sous la liste.":::

### <a name="network-documentation"></a>Documentation du réseau

Dans Microsoft Teams, il est nécessaire de disposer d’une connectivité Internet et au-dessous des conditions de réseau pour une expérience optimale.

Latence (RTT) < 300. Scintillement < 30ms | Perte de paquets < 1%

Comme indiqué plus haut, la qualité du contenu multimédia en temps réel sur un réseau IP est fortement affectée par la qualité de la connectivité du réseau, mais surtout par la quantité de :

- **Latence** -il s’agit du temps nécessaire à l’obtention d’un paquet IP du point A au point B sur le réseau. Ce délai de propagation du réseau est essentiellement lié à la distance physique entre les deux points et la vitesse de la lumière, y compris la surcharge supplémentaire prélevée par les différents routeurs entre eux. La latence est mesurée en temps réel de boucle.
- **Perte de paquets** : il s’agit généralement du pourcentage de paquets perdus dans une période donnée. La perte de paquets affecte directement la qualité audio (par rapport aux petits paquets perdus individuels qui n’ont presque aucun impact, en raison d’une perte de Burst en retour en continu qui engendre une coupure audio complète).
- **Scintillement** -il s’agit du changement moyen de délai entre les paquets successifs.

L’utilisation de données attendue à partir de Walk parle est entourée de 20KB/s lors de l’envoi ou de la réception d’audio. En cas d’inactivité, la durée de l’utilisation des données de Walkship parle est négligeable.

### <a name="walkie-talkie-devices"></a>Appareils de discussion

Les travailleurs terrain doivent souvent parler et recevoir des appels à propos de l’appel, même si leur téléphone est verrouillé. Cette expérimentation est possible via des appareils spécialisés avec un bouton PTT dédié.

- Téléphones existants
  - Casques câblés ([électronique Klein](https://www.kleinelectronics.com/))
  - Casques sans fil ([Jabra BlueParrott](https://www.blueparrott.com/))
- Des téléphones plus robustes
  - Samsung Galaxy XCover Pro
    - [Plus d’informations](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).
    - [Guide de configuration](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> Ces appareils ne sont pas des équipes certifiées. Elles ont été validées pour fonctionner avec le Guide de conversation de teams.

### <a name="license-requirements"></a>Conditions de licence

L’application de discussion à propos de Microsoft est incluse dans toutes les licences payantes d’équipes dans les [abonnements Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing). Pour plus d’informations sur l’obtention d’équipes, voir [Comment obtenir l’accès à Microsoft teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

> [!NOTE]
> Certaines fonctionnalités avancées pourront nécessiter des licences supplémentaires. Par exemple, l’intégration de Samsung Galaxy XCover Pro nécessite une licence Knox.

## <a name="further-information"></a>Informations complémentaires

- ITAdmins peut conserver le contrôle de qui utilise des stratégies de l’application.
- Si votre travailleur terrain utilise des données mobiles pour communiquer par le biais d’équipes, vous pouvez utiliser la même méthode.
- L’utilisation de la gestion des problèmes de bande passante devrait fonctionner correctement dans les situations de faible bande passante, ou dans les cas où votre smartphone est connecté et fonctionne. La discussion ne fonctionnera pas tant qu’il n’y a aucune connexion.

Pour en savoir plus sur l’utilisation des utilisateurs finaux, voir :

- [Commencer à utiliser teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Communiquer avec votre équipe grâce au Guide de conversation](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
