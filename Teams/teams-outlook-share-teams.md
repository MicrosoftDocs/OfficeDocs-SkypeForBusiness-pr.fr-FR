---
title: Partager dans Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez la fonctionnalité Partager dans Teams, qui permet aux utilisateurs de partager des e-mails et des pièces jointes à partir d’Outlook vers n’importe quelle conversation ou canal dans Teams.
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f8334f8dbdbebce17dea4a8a4ebc8ebf798b79
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198486"
---
# <a name="share-to-teams-from-outlook"></a>Partager dans Teams à partir d’Outlook

Partager dans Teams à partir d’Outlook (Partager vers Teams) permet aux utilisateurs de partager des e-mails, y compris des pièces jointes, à partir d’Outlook vers n’importe quelle conversation ou canal dans Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Complément Outlook pour le partage dans Teams 

La fonctionnalité Partager dans Teams nécessite un complément pour Outlook. Ce complément est installé automatiquement chaque fois qu’un utilisateur se connecte à l’application web Teams ou au client de bureau Teams.

> [!NOTE]
> Veillez à consulter [Les compléments pour Outlook dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) et [les règles d’accès au client dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) pour vous assurer que vos compléments pour Outlook fonctionnent correctement. En outre, la désactivation des expériences connectées peut empêcher les compléments pour Outlook de fonctionner correctement. Pour plus [d’informations, voir Expériences connectées dans Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) . Les boîtes aux lettres partagées ne sont pas prises en charge par le complément. 

Le partage vers Teams utilise le même mécanisme de transport que lorsqu’un utilisateur envoie un e-mail à un canal. Pour le partage dans des conversations, les e-mails (y compris les pièces jointes) sont copiés dans le OneDrive de l’expéditeur. Pour le partage sur des canaux, les e-mails et les pièces jointes sont copiés dans le dossier **Email messages** dans SharePoint.

Le complément Outlook pour le partage dans Teams utilise l’ensemble de conditions requises 1.7, comme indiqué dans [la documentation sur les compléments Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), qui inclut des détails sur les compléments Outlook, les conditions d’environnement requises pour les compléments Outlook et les clients Outlook spécifiques pris en charge avec l’ensemble de conditions requises 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Activation ou désactivation du partage dans Teams

Le complément Outlook pour Partager dans Teams peut être désactivé ou activé de manière sélective par utilisateur à l’aide des applets de commande PowerShell suivantes.

> [!NOTE]
> La désactivation du complément n’est possible qu’une fois le complément installé. Si vous souhaitez appliquer la désactivation pour tous les utilisateurs de votre locataire, exécutez un script régulièrement.

Pour désactiver le complément pour Outlook utilisé par Share to Teams, exécutez [l’applet de commande qui se trouve ici](/powershell/module/exchange/disable-app).

Pour activer le complément pour Outlook utilisé par Share to Teams, exécutez [l’applet de commande disponible ici](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Navigateurs et authentification unique

Partager avec Teams, dans les clients de bureau Outlook sur le web et Outlook, s’appuie sur un navigateur WebView. Pour plus d’informations sur les clients qui utilisent les navigateurs spécifiques, consultez [Navigateurs utilisés par les compléments Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) . 

> [!IMPORTANT]
> Partager avec Teams nécessite que les cookies tiers et l’accès au stockage local soient activés pour les navigateurs des utilisateurs.

Share to Teams utilise l’authentification unique (SSO), ce qui signifie que les utilisateurs n’ont pas besoin de fournir leurs informations d’identification lors de l’utilisation du complément via Partager dans Teams. L’authentification unique pour Outlook sur le web prend en charge <https://outlook.office365.com/owa/extSSO.aspx> et <https://outlook.office.com/owa/extSSO.aspx> les URL de réponse par défaut. Pour les domaines personnalisés, les administrateurs doivent ajouter l’URL de réponse Azure Active Directory appropriée.
