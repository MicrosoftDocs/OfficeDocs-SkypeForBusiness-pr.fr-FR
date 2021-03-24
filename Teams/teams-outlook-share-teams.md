---
title: Partager avec Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Découvrez la fonctionnalité Partager avec Teams, qui permet aux utilisateurs de partager des e-mails et des pièces jointes à partir d’Outlook dans n’importe quelle conversation ou canal dans Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098220"
---
# <a name="share-to-teams-from-outlook"></a>Partager dans Teams à partir d’Outlook

Partager avec Teams à partir d’Outlook (Partager avec Teams) permet aux utilisateurs de partager des e-mails, y compris des pièces jointes, à partir d’Outlook vers n’importe quelle conversation ou canal dans Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook add-in for Share to Teams 

La fonctionnalité Partager avec Teams nécessite un module pour Outlook. Ce module est installé automatiquement chaque fois qu’un utilisateur se connecte à l’application Web Teams ou au client de bureau Teams.

> [!NOTE]
> N’oubliez pas de passer en revue les [modules add-ins](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) pour Outlook dans Exchange Online et les règles d’accès client [dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) pour vous assurer que vos modules pour Outlook fonctionnent correctement. Par ailleurs, la désactivation des expériences connectées peut empêcher le fonctionnement correct des modules pour Outlook. Pour plus [d’informations, voir](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) Expériences connectées dans Office.  

Le partage avec Teams utilise le même mécanisme de transport que lorsqu’un utilisateur envoie un e-mail à un canal. Pour le partage de conversations, les messages électroniques (y compris les pièces jointes) sont copiés dans l’onedrive de l’expéditeur. Pour le partage dans les canaux, les messages électroniques et les pièces jointes sont copiés dans le dossier **Messages** électroniques dans SharePoint.

Le add-in Outlook pour Partager avec Teams utilise la condition requise définie 1.7, comme détaillé dans la documentation des [add-ins Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)qui comprend des détails sur les modules outlook, les conditions requises pour les environnements pour les add-ins Outlook et les clients Outlook spécifiques pris en charge avec l’exigence définie 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Activation ou désactivation du partage dans Teams

Le ajouter Outlook pour partager avec Teams peut être désactivé ou activé de manière sélective pour chaque utilisateur à l’aide des cmdlets PowerShell suivantes.

> [!NOTE]
> La désactivation du add-in n’est possible qu’une fois qu’il a été installé. Si vous voulez appliquer la désactivation pour tous les utilisateurs de votre client, exécutez un script régulièrement.

Pour désactiver le add-in pour Outlook utilisé par Partager avec Teams, exécutez [l’cmdlet trouvée ici.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Pour activer le add-in pour Outlook utilisé par Partager avec Teams, exécutez [l’cmdlet trouvée ici.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Navigateurs et sign-on unique

La fonction Partager avec Teams, dans les clients de bureau Outlook sur le web et Outlook, s’appuie sur un navigateur WebView. Pour plus d’informations sur les clients qui utilisent des [navigateurs spécifiques,](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) consultez les navigateurs utilisés par les modules détaillés. 

> [!IMPORTANT]
> Le partage avec Teams nécessite que les cookies tiers et l’accès au stockage local soient activés pour les navigateurs des utilisateurs.

La fonction Partager avec Teams utilise l' single sign-on (SSO), ce qui signifie que les utilisateurs n’ont pas besoin de fournir leurs informations d’identification lorsqu’ils utilisent le add-in via Share to Teams. L’os SSO pour Outlook sur le web prend en charge les URL de réponse et les prend https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx en charge par défaut. Pour les domaines personnel, les administrateurs doivent ajouter l’URL de réponse Azure Active Directory appropriée.