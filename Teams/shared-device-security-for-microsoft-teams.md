---
title: 'Guide de sécurité à confiance zéro pour Microsoft Teams : utiliser Teams en toute sécurité sur des ordinateurs partagés'
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Conseils à confiance zéro pour utiliser Microsoft Teams en toute sécurité à partir d'un ordinateur partagé sur le lieu de travail.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83fc071aa50ed076fc2a6798cfaee9d4770a36a5
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817675"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>Utiliser les Teams Microsoft en toute sécurité sur des ordinateurs partagés

Dans la mesure du possible *il est recommandé* aux entreprises d'adopter une approche de confiance zéro pour les appareils clients en utilisant les capacités de gestion des appareils, les contrôles de santé des appareils et l'application des politiques, le cryptage au niveau des appareils et d'autres caractéristiques de sécurité.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Image de confiance zéro montrant la vérification explicite, le moindre privilège, et l'hypothèse de violation -- les principes fondamentaux de confiance zéro -- dans les cercles bleus.":::

Les administrateurs peuvent créer des conditions sécurisées en *insistant* sur la vérification, les privilèges minimum, et en supposant des normes de compromission qui entraînent des actions qui réduisent les risques pour les utilisateurs et les données.

> [!TIP]
> Pour un examen plus approfondi des principes de la confiance zéro, voir [ces vidéos](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>Conseils pour utiliser Microsoft Teams en toute sécurité à partir d'un ordinateur partagé

Reconnaissant que cela peut ne pas être possible ou pratique dans tous les scénarios, il est toujours important que les administrateurs de la sécurité suivent les conseils pour utiliser au mieux Teams à partir d'un ordinateur partagé ou d'un appareil non géré.

Des plans doivent être élaborés pour se conformer aux lignes directrices aussi rapidement que possible.

1. Utiliser les capacités de sécurité de la plate-forme du système opérationnel.
    1. Assurez-vous que le système opérationnel est configuré pour installer les mises à jour automatiques du fournisseur du système opérationnel (pour les systèmes Microsoft, cela peut être fait via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)). 
    1. Assurez-vous que toutes les fonctionnalités de chiffrement d’appareil telles que [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) sont activées et que la clé utilisée pour accéder à l’appareil est sécurisée.  Notez que la plupart des [**appareils Windows 10 modernes prennent en charge bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10). 
    1. Utilisez des capacités anti-virus telles que celles offertes par [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) sur vos appareils.
    1. L'utilisation [de comptes d'utilisateur séparés ](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)pour chaque utilisateur du système est fortement recommandée.
    1. *Ne* pas accorder, ou utiliser, des privilèges d'administrateur pour des fonctions non administratives (telles que la navigation sur le web, la gestion des Teams etc).

Si les instructions ci-dessus ne peuvent pas être satisfaites, nous vous recommandons d’utiliser d’autres meilleures pratiques de sécurité de navigateur :

1. Appliquez les fonctionnalités de sécurité du navigateur.
    1. Utilisez des sessions de navigation privées pour minimiser les données et l'historique qui persistent sur le disque. Par exemple, utilisez [la navigation inPrivate dans Microsoft Edge ](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [ la navigation Incognito dans Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), ou les capacités de votre navigateur spécifique pour la navigation privée.
    1. Il est recommandé de changer le comportement du système afin d'engager la navigation privée *par défaut*.

2. Naviguez et utilisez [l'application web Teams](https://teams.microsoft.com) (parfois appelée le  *client* web) et non le client téléchargeable Teams.

3. Lorsque vous avez fini d'utiliser le système partagé, vous devez :
    1. [ Déconnexion des Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    1. Fermez tous les onglets et fenêtres du navigateur.
    1. Déconnectez-vous de l'appareil.

Les éléments ci-dessus ne sont pas une liste complète des meilleures pratiques ou des contrôles de sécurité couvrant tous les cas, et il peut y avoir des actions supplémentaires qui peuvent être effectuées dans votre environnement (par exemple, les administrateurs de sécurité peuvent choisir d’utiliser des liens fiables et des pièces jointes fiables pour Teams si vous avez [Microsoft Defender pour Office 365 Plan 1 ou Plan 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide)). Toutefois, ces étapes constituent un point de départ pour l’élaboration de conseils sur l’utilisation de Teams à partir d’appareils partagés.

## <a name="more-information"></a>Plus d'informations

[BitLocker dans Gestionnaire de configuration](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[BitLocker pour Windows 10 dans Intune](/mem/intune/protect/encrypt-devices)

[Sécurité des terminaux dans Intune](/mem/intune/protect/endpoint-security)

[Activez](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app)l'antivirus Microsoft Defender dans votre sécurité Windows et[lancez des analyses](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[ Article du centre de sécurité Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[ Client web Teams/application web des équipes ](./get-clients.md#browser-client)

[ Sécurité et Microsoft Team](./teams-security-guide.md)
