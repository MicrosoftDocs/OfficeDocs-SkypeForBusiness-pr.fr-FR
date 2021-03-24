---
title: Déploiements locaux à forêts multiples de Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement local à forêts multiples.
ms.openlocfilehash: d215ce13059c414d6c6142d7cd1e93ea9011c97b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093528"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="7a200-103">Déploiements locaux à forêts multiples de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="7a200-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="7a200-104">Lisez cette rubrique pour découvrir comment déployer Skype Room System dans un environnement local à forêts multiples.</span><span class="sxs-lookup"><span data-stu-id="7a200-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a200-105">Pour pouvoir être déployé dans plusieurs forêts, Skype Room System nécessite Exchange Server CU6 2013 publiée le 26 août 2014.</span><span class="sxs-lookup"><span data-stu-id="7a200-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="7a200-106">Évitez de ré-utiliser une boîte aux lettres existante pour Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="7a200-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="7a200-107">Utilisez une nouvelle boîte aux lettres de ressources (supprimer l’ancienne boîte aux lettres et la re-créer) pour Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="7a200-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="7a200-108">Pour restaurer les réunions perdues en supprimant la boîte aux lettres, voir Connecter ou [restaurer une boîte aux lettres supprimée.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="7a200-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span></span> 
  
<span data-ttu-id="7a200-109">Après avoir créé la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing pour configurer la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="7a200-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="7a200-110">Pour plus d’informations, reportez-vous aux étapes 3 à 6 sous Déploiements locaux à forêt unique.</span><span class="sxs-lookup"><span data-stu-id="7a200-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="7a200-111">Après avoir créé une boîte aux lettres de ressources Exchange pour Skype Room System, activez le compte pour Skype Entreprise en suivant les étapes de la procédure d’activation des comptes Skype Room System pour Skype Entreprise dans le cadre de déploiements locaux à forêt unique.</span><span class="sxs-lookup"><span data-stu-id="7a200-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="7a200-112">Option 1 : Créer une boîte aux lettres de ressources</span><span class="sxs-lookup"><span data-stu-id="7a200-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="7a200-113">Pour déployer Skype Room System dans un environnement à forêts multiples :</span><span class="sxs-lookup"><span data-stu-id="7a200-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="7a200-114">Créez un utilisateur lié (LinkedRoomTest) dans Active Directory (forêt d’authentification).</span><span class="sxs-lookup"><span data-stu-id="7a200-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="7a200-115">Exécutez les commandes suivantes dans Exchange Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="7a200-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="7a200-116">Option 2 : Modifier une boîte aux lettres de salle existante en boîte aux lettres de ressources Skype Room System (liée)</span><span class="sxs-lookup"><span data-stu-id="7a200-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```