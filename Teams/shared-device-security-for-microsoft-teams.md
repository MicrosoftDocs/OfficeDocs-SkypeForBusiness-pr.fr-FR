---
title: Guide de sécurité pour Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Conseils pour utiliser Microsoft Teams en toute sécurité à partir d'un ordinateur partagé sur le lieu de travail.
localization_priority: Priority
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
ms.openlocfilehash: a723a7300febde4eaa5045b9b1318a3e0cafe779
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860828"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>Utiliser les Teams Microsoft en toute sécurité sur des ordinateurs partagés

Dans la mesure du possible*il est recommandé* aux entreprises d'adopter une approche de confiance zéro pour les appareils clients en utilisant les capacités de gestion des appareils, les contrôles de santé des appareils et l'application des politiques, le cryptage au niveau des appareils et d'autres caractéristiques de sécurité.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Image de confiance zéro montrant la vérification explicite, le moindre privilège, et l'hypothèse de violation -- les principes fondamentaux de confiance zéro -- dans les cercles bleus.":::

Les administrateurs peuvent créer des conditions très sûres en *insistant* sur la vérification, le moindre privilège, et en assumant des compromis -- des normes qui conduisent à des actions qui minimisent les risques à la fois pour les utilisateurs et les données.

> [!TIP]
> Pour un examen plus approfondi des principes de la confiance zéro, voir [ces vidéos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>Conseils pour utiliser Microsoft Teams en toute sécurité à partir d'un ordinateur partagé

Reconnaissant que cela peut ne pas être possible ou pratique dans tous les scénarios, il est toujours important que les administrateurs de la sécurité suivent les conseils pour utiliser au mieux Teams à partir d'un ordinateur partagé ou d'un appareil non géré.

Des plans doivent être élaborés pour se conformer aux lignes directrices aussi rapidement que possible.

1. Utiliser les capacités de sécurité de la plate-forme du système opérationnel.
    1. Assurez-vous que le système opérationnel est configuré pour installer les mises à jour automatiques du fournisseur du système opérationnel (pour les systèmes Microsoft, cela peut être fait via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)). 
    2. Assurez-vous que toutes les capacités de cryptage de l'appareil, telles que le[**bitlocker**](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) sont activées et que la clé utilisée pour accéder à l'appareil est sécurisée.
    1. Utilisez des capacités anti-virus telles que celles offertes par [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) sur vos appareils.
    1. L'utilisation [de comptes d'utilisateur séparés ](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)pour chaque utilisateur du système est fortement recommandée.
    1. *Ne*pas accorder, ou utiliser, des privilèges d'administrateur pour des fonctions non administratives (telles que la navigation sur le web, la gestion des Teams etc).

2. Exploiter les capacités de sécurité du navigateur.
    1. Utilisez des sessions de navigation privées pour minimiser les données et l'historique qui persistent sur le disque. Par exemple, utilisez [la navigation inPrivate dans Microsoft Edge ](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [ la navigation Incognito dans Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), ou les capacités de votre navigateur spécifique pour la navigation privée. 
    1. Il est recommandé de changer le comportement du système afin d'engager la navigation privée*par défaut*. 

3. Naviguez et utilisez [l'application web Teams](https://teams.microsoft.com) (parfois appelée le  *client* web) et non le client téléchargeable Teams.

4. Lorsque vous avez fini d'utiliser le système partagé, vous devez : 
    1. [ Déconnexion des Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    1. Fermez tous les onglets et fenêtres du navigateur.
    1. Déconnectez-vous de l'appareil.

Les éléments ci-dessus ne constituent pas une liste exhaustive des meilleures pratiques ou des contrôles de sécurité couvrant tous les cas, et il se peut que des mesures supplémentaires puissent être prises dans votre environnement (par exemple, les administrateurs de la sécurité peuvent choisir d'utiliser des liens et des pièces jointes sûrs pour les Teams si vous avez [Office 365 ATP Plan 1 ou 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)). Toutefois, ces étapes constituent un point de départ pour l'élaboration de conseils sur l'utilisation des équipes à partir de dispositifs partagés.

## <a name="more-information"></a>Plus d'informations

[Bitlocker dans le gestionnaire de configuration](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[Bitlocker pour Windows 10 dans Intune](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[Sécurité des terminaux dans Intune](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

[Activez](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app)l'antivirus Microsoft Defender dans votre sécurité Windows et[lancez des analyses](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[ Article du centre de sécurité Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[ Client web Teams/application web des équipes ](../get-clients.md#web-client)

[ Sécurité et Microsoft Team](https://docs.microsoft.com/microsoftteams/teams-security-guide)
