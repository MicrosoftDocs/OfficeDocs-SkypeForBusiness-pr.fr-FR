---
title: Gérer les comptes de ressource dans Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: Dans cet article, vous allez apprendre à créer, modifier et gérer des comptes de ressources dans Microsoft Teams.
ms.openlocfilehash: 176cf304909094ae12c102f26ccbcd777366b649
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124159"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gérer les comptes de ressources dans Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Étapes suivantes

Une fois que vous avez terminé la configuration du compte de ressource et affecté un numéro de service si nécessaire, vous êtes prêt à utiliser le compte de ressource avec un standard automatique ou une file d’attente d’appels.

Pour en savoir plus, consultez les références suivantes :

- [Standard automatique cloud](create-a-phone-system-auto-attendant.md)
- [File d’attente d’appels cloud](create-a-phone-system-call-queue.md)

Vous pouvez modifier le **nom d’affichage** du compte de ressource et le type de **compte de ressource** à l’aide de l’option **Modifier** . Cliquez sur **Enregistrer** lorsque vous avez terminé.

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>Modifier un compte de ressource existant pour utiliser une licence d’utilisateur virtuel

Si vous décidez de basculer les licences sur votre compte de ressources existant d’une licence **Téléphonie Teams standard** vers une licence d’utilisateur virtuel, vous devez acquérir la licence d’utilisateur virtuel gratuite, puis suivre les étapes de la Centre d'administration Microsoft 365 pour [déplacer les utilisateurs vers un autre abonnement](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Supprimez toujours une licence Téléphonie Teams standard complète et attribuez la licence Utilisateur virtuel dans la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications apportées au compte, ajoutez la nouvelle licence, puis enregistrez à nouveau les paramètres du compte, le compte de ressource peut ne plus fonctionner comme prévu. Si cela se produit, nous vous recommandons de créer un compte de ressource pour la licence d’utilisateur virtuel et de supprimer le compte de ressource rompu.

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

Pour les comptes de ressources hébergés sur Skype For Business Server 2019 qui peuvent être utilisés avec des files d’attente d’appels cloud et des standards automatiques cloud, consultez [Plan Cloud Call Queues](/SkypeforBusiness/hybrid/plan-call-queue) ou [Plan Cloud Auto Attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Les implémentations hybrides (numéros hébergés sur le routage direct) sont configurées à l’aide de l’applet de commande [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) sur un serveur local Skype Entreprise Server 2019.

Les ID d’application que vous devez utiliser lors de la création des instances d’application sont les suivants :

- **Standard automatique :** ce933385-9390-45d1-9512-c8d228074e07
- **File d’attente d’appels :** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Si vous souhaitez que la file d’attente des appels ou le standard automatique puisse être recherché par les utilisateurs de Skype For Business Server 2019, vous devez créer vos comptes de ressources sur Skype For Business Server 2019, car les comptes de ressources en ligne ne sont pas synchronisés avec Active Directory. Lorsque les enregistrements SRV DNS pour sipfederationtls sont résolus en Skype Entreprise Server 2019, les comptes de ressources **doivent** être créés sur Skype For Business Server 2019 à l’aide de l’interpréteur de commandes SfB Management et synchronisés avec Azure AD.

Pour les implémentations hybrides avec Skype Entreprise Server :

   [Planifier les standards automatiques cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [Planifier les files d’attente d’appels cloud](/SkypeforBusiness/hybrid/plan-call-queue)

   [Configurer des comptes de ressources local](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>Supprimer un compte de ressource

Veillez à dissocier le numéro de téléphone du compte de ressource avant de le supprimer, afin d’éviter que votre numéro de service ne soit bloqué en mode en attente.

Après cela, vous pouvez supprimer le compte de ressource dans le Centre d'administration Microsoft 365, sous l’onglet Utilisateurs.

Pour dissocier un numéro de téléphone de routage direct du compte de ressource, utilisez l’applet de commande suivante :

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
