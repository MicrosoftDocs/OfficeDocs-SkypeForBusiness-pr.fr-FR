---
title: Erreurs de canaux partagés dans Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: Découvrez comment utiliser la résolution des erreurs dans les canaux partagés dans Microsoft Teams.
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024143"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Erreurs de canaux partagés dans Microsoft Teams

Si vos utilisateurs voient des messages d’erreur lors de la tentative d’ajout de personnes extérieures à votre organisation à des canaux partagés, vérifiez les paramètres de cet article. 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>En raison de la stratégie d’administration, vous ne pouvez pas ajouter de personnes externes au canal. Pour plus d’informations, contactez votre administrateur.

Teams utilise Groupes Microsoft 365 pour l’appartenance à l’équipe. Les paramètres d’invité Groupes Microsoft 365 doivent être activés pour que les personnes extérieures à l’organisation soient ajoutées à un canal partagé. Si vos utilisateurs voient cette erreur, vérifiez les paramètres Groupes Microsoft 365 pour les personnes extérieures à l’organisation.

Pour définir Groupes Microsoft 365 paramètres pour les personnes extérieures à l’organisation
1. Dans le Centre d'administration Microsoft 365, dans le volet de navigation gauche, **développez Paramètres**.
1. Cliquez sur **Paramètres de l’organisation**.
1. Dans la liste, cliquez sur **Groupes Microsoft 365**.
1. Vérifiez que les **cases à cocher Autoriser les propriétaires de groupes à ajouter des personnes extérieures à votre organisation à Groupes Microsoft 365 en tant qu’invités** et **que les membres du groupe invité** accèdent aux cases à cocher de contenu du groupe.
1. Si vous avez apporté des modifications, cliquez sur **Enregistrer les modifications**.

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>En raison de la stratégie d’administration, vous ne pouvez pas ajouter de personnes externes au canal

Les stratégies de canal Teams déterminent comment les utilisateurs peuvent interagir avec les canaux partagés. Si les utilisateurs voient ce message d’erreur, vérifiez la stratégie de canal de cet utilisateur.

Pour définir la stratégie d’invitation de personnes extérieures à l’organisation à des canaux partagés
1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux stratégies Teams > Teams.
1. Sélectionnez la stratégie à laquelle votre utilisateur est affecté.
1. Assurez-vous que **l’option Inviter des utilisateurs externes à des canaux partagés** est **activée**.
1. Si vous avez apporté des modifications, **sélectionnez Appliquer**.

Pour plus d’informations sur les stratégies de canal Teams, consultez [Gérer les stratégies de canal dans Microsoft Teams](teams-policies.md).

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>Vous ne pouvez pas partager ce canal avec des personnes de cette organisation

Si vos utilisateurs voient cette erreur, ils ne peuvent pas partager le canal avec des personnes de l’autre organisation par les paramètres d’accès interlocataire Azure Active Directory. Cela peut être dû aux paramètres entrants de votre organisation ou aux paramètres sortants de l’autre organisation.

Pour vérifier les paramètres entrants de votre organisation
1. Dans [Azure Active Directory](https://aad.portal.azure.com), sélectionnez **Identités externes**, puis les **paramètres d’accès entre locataires**.
1. Sélectionnez le lien d’accès entrant pour l’organisation que vous souhaitez vérifier.
1. Sous l’onglet **Connexion directe B2B** , choisissez **Personnaliser les paramètres**.
1. Sous l’onglet **Utilisateurs et groupes externes** , **assurez-vous que l’option Autoriser l’accès** et **tous les utilisateurs et groupes externes** sont sélectionnés, ou si vous avez choisi **Sélectionner des utilisateurs et des groupes externes**, assurez-vous que l’utilisateur invité est membre des groupes sélectionnés.
1. Si vous avez apporté des modifications, **sélectionnez Enregistrer** et fermez le panneau **Paramètres d’accès entrant** .

Si les utilisateurs continuent de voir l’erreur, vérifiez auprès de l’organisation avec laquelle ils collaborent. Les paramètres sortants de cette organisation peuvent interdire le partage avec votre organisation. Pour plus d’informations sur la configuration de canaux partagés entre les organisations, consultez [Collaborer avec des participants externes dans un canal partagé](/microsoft-365/solutions/collaborate-teams-direct-connect).

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>Nous n’avons trouvé aucune correspondance. Vérifiez que l’adresse e-mail est correcte ou contactez votre administrateur.

Si vos utilisateurs voient cette erreur, Microsoft 365 n’est pas en mesure de trouver l’adresse e-mail spécifiée dans l’organisation externe. Vous devez confirmer l’adresse auprès de l’organisation externe.

