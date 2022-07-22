---
title: Partager avec Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez la fonctionnalité Partager vers Teams, qui permet aux utilisateurs de partager des e-mails et des pièces jointes d’Outlook vers n’importe quel canal ou conversation dans Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2ac9a38e16000829b391e77dffdd718ed349299
ms.sourcegitcommit: f5546acf02ec644225f6d0fb41f38b1912da6adf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66952758"
---
# <a name="share-to-teams-from-outlook"></a>Partager vers Teams à partir d’Outlook

Partager vers Teams à partir d’Outlook (Partager vers Teams) permet aux utilisateurs de partager des e-mails, y compris des pièces jointes, d’Outlook vers n’importe quelle conversation ou canal dans Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Complément Outlook pour Partager vers Teams 

La fonctionnalité Partager vers Teams nécessite un complément pour Outlook. Ce complément est installé automatiquement chaque fois qu’un utilisateur se connecte à l’application web Teams ou au client de bureau Teams.

> [!NOTE]
> Veillez à consulter [les compléments pour Outlook dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) et [les règles d’accès client dans Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) pour vous assurer que vos compléments pour Outlook fonctionnent correctement. En outre, la désactivation des expériences connectées peut empêcher les compléments pour Outlook de fonctionner correctement. Pour plus d’informations, consultez [Expériences connectées dans Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) . Les boîtes aux lettres partagées ne sont pas prises en charge par le complément. 

Le partage vers Teams utilise le même mécanisme de transport que lorsqu’un utilisateur envoie un e-mail à un canal. Pour le partage vers des conversations, les e-mails (y compris les pièces jointes) sont copiés sur OneDrive de l’expéditeur. Pour le partage sur des canaux, les e-mails et les pièces jointes sont copiés dans le dossier **Email messages** dans SharePoint.

Le complément Outlook pour Share to Teams utilise l’ensemble de conditions requises 1.7, comme détaillé dans la [documentation des compléments Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), qui inclut des détails sur les compléments Outlook, les exigences d’environnement pour les compléments Outlook et les clients Outlook spécifiques pris en charge avec l’ensemble de conditions requises 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Activation ou désactivation de Share to Teams

Le complément Outlook pour Share to Teams peut être désactivé de manière sélective ou activé par utilisateur à l’aide des applets de commande PowerShell suivantes.

> [!NOTE]
> La désactivation du complément n’est possible qu’une fois le complément installé. Si vous souhaitez appliquer la désactivation pour tous les utilisateurs de votre locataire, exécutez régulièrement un script.

Pour désactiver le complément pour Outlook utilisé par Share to Teams, exécutez [l’applet de commande trouvée ici](/powershell/module/exchange/disable-app).

Pour activer le complément pour Outlook utilisé par Share to Teams, exécutez [l’applet de commande trouvée ici](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Navigateurs et authentification unique

Share to Teams, à la fois dans les clients de bureau Outlook sur le web et Outlook, s’appuie sur un navigateur WebView. Consultez [Navigateurs utilisés par les compléments Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) pour plus d’informations sur les clients qui utilisent des navigateurs spécifiques. 

> [!IMPORTANT]
> Le partage vers Teams nécessite que les cookies tiers et l’accès au stockage local soient activés pour les navigateurs des utilisateurs.

Share to Teams utilise l’authentification unique (SSO), ce qui signifie que les utilisateurs n’ont pas besoin de fournir leurs informations d’identification lors de l’utilisation du complément via Share to Teams. L’authentification unique pour Outlook sur le web prend en charge <https://outlook.office365.com/owa/extSSO.aspx> et <https://outlook.office.com/owa/extSSO.aspx> répond aux URL par défaut. Pour les domaines de vanité, les administrateurs doivent ajouter l’URL de réponse Azure Active Directory appropriée.
