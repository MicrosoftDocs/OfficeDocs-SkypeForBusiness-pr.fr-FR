---
title: Partager en Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Découvrez la fonctionnalité Partager avec Teams qui permet aux utilisateurs de partager des courriers électroniques et des pièces jointes à partir d’Outlook vers une conversation ou un canal dans Teams.
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
# <a name="share-to-teams-from-outlook"></a>Partager du Teams à partir de Outlook

Partager vers Teams à partir d’Outlook (Partager vers Teams) permet aux utilisateurs de partager des messages électroniques, y compris des pièces jointes, de Outlook à une conversation ou un canal dans Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook le partage avec les Teams 

La fonctionnalité Partager Teams nécessite un module pour les Outlook. Ce module est installé automatiquement chaque fois qu’un utilisateur se connecte à l’application Teams Web ou au client Teams bureau.

> [!NOTE]
> N’oubliez pas de passer en revue les Outlook dans [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) et les règles d’accès client dans [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) pour vous assurer que vos Outlook fonctionnent correctement. Par ailleurs, la désactivation des expériences connectées peut empêcher le fonctionnement correct des Outlook pour les utilisateurs. Pour [plus d’informations, voir Expériences connectées Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) en savoir plus.  

La boîte de Teams utilise le même mécanisme de transport que lorsqu’un utilisateur envoie un e-mail à un canal. Pour le partage de conversations, les messages électroniques (y compris les pièces jointes) sont copiés dans la boîte aux OneDrive de l’OneDrive. Pour le partage dans les canaux, les e-mails et pièces jointes sont copiés dans le dossier **Messages** électroniques dans SharePoint.

Le Outlook pour partager vers Teams utilise l’exigence 1.7, comme détaillé dans la documentation des [modules](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)Outlook, qui comprend des détails sur les Outlook, les exigences d’environnement pour les Outlook et les clients Outlook spécifiques pris en charge avec l’exigence définie 1,7.

## <a name="enabling-or-disabling-share-to-teams"></a>Activation ou désactivation de l’action Partager sur Teams

Le Outlook pour le partage à Teams peut être désactivé ou activé de manière sélective pour chaque utilisateur à l’aide des cmdlets PowerShell suivantes.

> [!NOTE]
> La désactivation du add-in n’est possible qu’une fois qu’il a été installé. Si vous voulez appliquer la désactivation pour tous les utilisateurs de votre client, exécutez un script régulièrement.

Pour désactiver le Outlook utilisé par Share to Teams, exécutez [l’cmdlet trouvée ici.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Pour activer le Outlook utilisé par Share to Teams, exécutez [l’cmdlet trouvée ici.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Navigateurs et sign-on unique

La fonction Partager Teams, dans Outlook sur le web et Outlook bureau, utilise un navigateur WebView. Pour plus d’informations sur les clients qui utilisent des [navigateurs spécifiques,](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) voir Navigateurs utilisés Office par défaut. 

> [!IMPORTANT]
> Le partage Teams nécessite que les cookies tiers et l’accès au stockage local soient activés pour les navigateurs des utilisateurs.

La fonction Partager vers Teams utilise l' signer unique, ce qui signifie que les utilisateurs n’ont pas besoin de fournir leurs informations d’identification lors de l’utilisation du module via l’outil Partager Teams. L' serveur de Outlook sur le web prend en charge les URL de réponse et les prend https://outlook.office365.com/owa/extSSO.aspx https://outlook.office.com/owa/extSSO.aspx en charge par défaut. Pour les domaines personnel, les administrateurs doivent ajouter les adresses appropriées Azure Active Directory’URL de réponse.