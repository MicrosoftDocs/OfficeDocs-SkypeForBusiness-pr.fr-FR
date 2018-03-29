---
title: Déploiements locaux de plusieurs forêts Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.
ms.openlocfilehash: b5a0a2615f8174ea5e7d56dcaf0830765365bb48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="596ab-103">Déploiements locaux de plusieurs forêts Skype Room System</span><span class="sxs-lookup"><span data-stu-id="596ab-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="596ab-104">Consultez cette rubrique pour apprendre à déployer Skype Room System dans un environnement local à plusieurs forêts.</span><span class="sxs-lookup"><span data-stu-id="596ab-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="596ab-105">Pour le déploiement dans plusieurs forêts, Skype espace système nécessite Exchange Server 2013 CU6, publié le 26 août 2014.</span><span class="sxs-lookup"><span data-stu-id="596ab-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="596ab-106">Évitez de nouveau à l’aide d’une boîte aux lettres existante pour système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="596ab-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="596ab-107">Utiliser une nouvelle (supprimer l’ancienne boîte aux lettres et les recréer) boîte aux lettres de ressources pour le système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="596ab-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="596ab-108">Pour restaurer les réunions perdues lors de la suppression de la boîte aux lettres, voir [se connecter ou restaurer une boîte aux lettres supprimée](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="596ab-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="596ab-109">Après la création de la boîte aux lettres, vous pouvez utiliser Set-CalendarProcessing pour configurer la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="596ab-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="596ab-110">Reportez-vous aux étapes 3 à 6 sous Déploiements locaux dans une forêt unique pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="596ab-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="596ab-111">Après la création d’une boîte aux lettres de ressource Exchange pour système de salle de Skype, activer le compte pour Skype pour entreprise, en suivant les étapes de l’activation de comptes de système salle Skype pour Skype pour les entreprises dans les déploiements sur site de forêt unique.</span><span class="sxs-lookup"><span data-stu-id="596ab-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="596ab-112">Option 1 : créer une nouvelle boîte aux lettres de ressources</span><span class="sxs-lookup"><span data-stu-id="596ab-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="596ab-113">Pour déployer le système d’espace Skype dans un environnement à plusieurs forêts :</span><span class="sxs-lookup"><span data-stu-id="596ab-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="596ab-114">Créez un utilisateur lié (LinkedRoomTest) dans Active Directory (forêt d’authentification).</span><span class="sxs-lookup"><span data-stu-id="596ab-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="596ab-115">Exécutez les commandes suivantes dans le Exchange Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="596ab-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="596ab-116">Option 2 : Modifier une boîte aux lettres de salle existant pour la boîte aux lettres de la ressource (liée) système de salle de Skype</span><span class="sxs-lookup"><span data-stu-id="596ab-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1

```


