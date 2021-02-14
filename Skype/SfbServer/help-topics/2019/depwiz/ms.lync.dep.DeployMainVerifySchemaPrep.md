---
title: Vérifier la réplication de la partition du schéma
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour vérifier que l’extension de schéma a bien été répliquée dans votre forêt des services de domaine Active Directory, faites les choses suivantes :'
ms.openlocfilehash: 4e4bfdf4fb50366f831f029d8f331551ba906969
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801564"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="f9aac-103">Vérifier la réplication de la partition du schéma</span><span class="sxs-lookup"><span data-stu-id="f9aac-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="f9aac-104">Pour vérifier que l’extension de schéma a bien été répliquée dans votre forêt des services de domaine Active Directory, faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="f9aac-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="f9aac-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span><span class="sxs-lookup"><span data-stu-id="f9aac-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="f9aac-106">Ouvrez l’éditeur ADSI : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Modification ADSI**.</span><span class="sxs-lookup"><span data-stu-id="f9aac-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f9aac-107">Vous pouvez également cliquer sur **Démarrer**, puis sur **Exécuter**, et taper **adsiedit.msc** pour démarrer l’éditeur ADSI.</span><span class="sxs-lookup"><span data-stu-id="f9aac-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="f9aac-108">Dans l’arborescence de la console MMC, s’il n'est pas encore sélectionné, cliquez sur Modification ADSI.</span><span class="sxs-lookup"><span data-stu-id="f9aac-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="f9aac-109">Dans le menu **Action**, cliquez sur **Se connecter à**.</span><span class="sxs-lookup"><span data-stu-id="f9aac-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="f9aac-110">Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9aac-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="f9aac-p101">Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion. Si cet objet existe et si la valeur de l’attribut **rangeUpper** est 1150 et si la valeur de l’attribut **rangeLower** est 3, cela signifie que le schéma a été mis à jour et répliqué avec succès. Si cet objet n’existe pas ou si la valeur des attributs **rangeUpper** et **rangeLower** n’est pas spécifiée, cela signifie que le schéma n’a pas été modifié ou n’a pas été répliqué.</span><span class="sxs-lookup"><span data-stu-id="f9aac-p101">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion. If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated. If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f9aac-114">Si, lorsque vous recherchez la réplication du schéma, celle-ci n’apparaît pas comme ayant abouti, patientez environ 15 minutes avant de réessayer.</span><span class="sxs-lookup"><span data-stu-id="f9aac-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="f9aac-115">La réplication Active Directory est basée sur un modèle de cohérence souple et une certaine latence de réplication peut se produire, en fonction d’un certain nombre de facteurs dans le serveur et l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="f9aac-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

