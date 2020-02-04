---
title: Vérifier la réplication de la partition du schéma
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour vérifier que l’extension de schéma a bien été répliquée dans votre forêt services de domaine Active Directory (AD FS), procédez comme suit :'
ms.openlocfilehash: 2d739bece89d43d5d3be289be55c90c2a63b49fe
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705339"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="bedca-103">Vérifier la réplication de la partition du schéma</span><span class="sxs-lookup"><span data-stu-id="bedca-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="bedca-104">Pour vérifier que l’extension de schéma a bien été répliquée dans votre forêt services de domaine Active Directory (AD FS), procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bedca-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="bedca-105">Ouvrez une session sur un contrôleur de domaine (autre que le contrôleur de domaine qui contient le rôle de maître de schéma) dans votre forêt services de domaine Active Directory (AD DS), où les extensions de schéma étaient appliquées en tant que membre du groupe administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="bedca-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="bedca-106">Ouvrez ADSI Edit : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **modification ADSI**.</span><span class="sxs-lookup"><span data-stu-id="bedca-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="bedca-107">Vous pouvez également cliquer sur **Démarrer**, puis sur **exécuter**, taper **adsied. msc** pour démarrer ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="bedca-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="bedca-108">Dans l’arborescence Microsoft Management Console (MMC), si ce n’est pas déjà fait, cliquez sur ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="bedca-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="bedca-109">Dans le menu **Action**, cliquez sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="bedca-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="bedca-110">Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bedca-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="bedca-111">Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="bedca-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="bedca-112">Si cet objet existe et que la valeur de l’attribut **rangeUpper** est 1150 et que la valeur de l’attribut **rangeLower** est 3, le schéma a été correctement mis à jour et répliqué.</span><span class="sxs-lookup"><span data-stu-id="bedca-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="bedca-113">Si cet objet n’existe pas ou si les valeurs des attributs **rangeUpper** et **rangeLower** ne sont pas spécifiées, le schéma n’a pas été modifié ou n’a pas été répliqué.</span><span class="sxs-lookup"><span data-stu-id="bedca-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bedca-114">Si votre vérification de la réplication du schéma ne montre pas encore de réussite, attendez environ 15 minutes avant de procéder à la vérification.</span><span class="sxs-lookup"><span data-stu-id="bedca-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="bedca-115">La réplication Active Directory est basée sur un modèle de cohérence faible et une latence de réplication peut se produire en fonction de plusieurs facteurs du serveur et de l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="bedca-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

