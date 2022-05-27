---
title: Partager vers Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez la fonctionnalité Partager vers Teams, qui permet aux utilisateurs de partager des e-mails et des pièces jointes de Outlook vers n’importe quelle conversation ou canal dans Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682025"
---
# <a name="share-to-teams-from-outlook"></a>Partager vers Teams à partir de Outlook

Partager vers Teams à partir de Outlook (Partager vers Teams) permet aux utilisateurs de partager des e-mails, y compris des pièces jointes, de Outlook à n’importe quelle conversation ou canal dans Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>complément Outlook pour Partager vers Teams 

La fonctionnalité Partager vers Teams nécessite un complément pour Outlook. Ce complément est installé automatiquement chaque fois qu’un utilisateur se connecte à l’application web Teams ou au client de bureau Teams.

> [!NOTE]
> Veillez à consulter [les compléments pour Outlook dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) et [les règles d’accès client dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) pour vous assurer que vos compléments pour Outlook fonctionnent correctement. En outre, la désactivation des expériences connectées peut empêcher les compléments pour Outlook de fonctionner correctement. Pour plus d’informations, consultez [Expériences connectées dans Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c).  

Partager pour Teams utilise le même mécanisme de transport que lorsqu’un utilisateur envoie un e-mail à un canal. Pour le partage de conversations, les e-mails (y compris les pièces jointes) sont copiés dans le OneDrive de l’expéditeur. Pour le partage sur des canaux, les e-mails et les pièces jointes sont copiés dans le dossier **Courrier électronique** dans SharePoint.

Le complément Outlook pour Share to Teams utilise l’ensemble de conditions requises 1.7, comme indiqué dans [Outlook documentation sur les compléments](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), qui inclut des détails sur Outlook compléments, les exigences d’environnement pour Outlook compléments et les clients Outlook spécifiques pris en charge avec l’ensemble de conditions requises 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Activation ou désactivation de Share pour Teams

Le complément Outlook pour Partager vers Teams peut être désactivé ou activé de manière sélective par utilisateur à l’aide des applets de commande PowerShell suivantes.

> [!NOTE]
> La désactivation du complément n’est possible qu’une fois le complément installé. Si vous souhaitez appliquer la désactivation pour tous les utilisateurs de votre locataire, exécutez régulièrement un script.

Pour désactiver le complément pour Outlook utilisé par Share pour Teams, exécutez [l’applet de commande trouvée ici](/powershell/module/exchange/disable-app).

Pour activer le complément pour Outlook utilisé par Share pour Teams, exécutez [l’applet de commande trouvée ici](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Navigateurs et authentification unique

Partager vers Teams, à la fois dans Outlook sur le web et Outlook clients de bureau, s’appuie sur un navigateur WebView. Consultez [Navigateurs utilisés par Office compléments](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) pour plus d’informations sur les clients qui utilisent des navigateurs spécifiques. 

> [!IMPORTANT]
> Le partage vers Teams nécessite que les cookies tiers et l’accès au stockage local soient activés pour les navigateurs des utilisateurs.

Share to Teams utilise l’authentification unique (SSO), ce qui signifie que les utilisateurs n’ont pas besoin de fournir leurs informations d’identification lors de l’utilisation du complément via Share pour Teams. L’authentification unique pour Outlook sur le web prend en charge <https://outlook.office365.com/owa/extSSO.aspx> et <https://outlook.office.com/owa/extSSO.aspx> répond aux URL par défaut. Pour les domaines de vanité, les administrateurs doivent ajouter l’URL de réponse Azure Active Directory appropriée.
