---
title: Vérification de la réplication de la Partition de schéma
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Pour vérifier que l’extension de schéma ont été correctement répliqués dans votre forêt des Services de domaine Active Directory, effectuez les opérations suivantes :'
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="ffb74-103">Vérification de la réplication de la Partition de schéma</span><span class="sxs-lookup"><span data-stu-id="ffb74-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="ffb74-104">Pour vérifier que l’extension de schéma ont été correctement répliqués dans votre forêt des Services de domaine Active Directory, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ffb74-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="ffb74-105">Ouvrez une session sur un contrôleur de domaine (autre que le contrôleur de domaine qui détient le rôle de maître de schéma) dans votre forêt des Services de domaine Active Directory, où les extensions de schéma ont été appliquées en tant que membre du groupe Administrateurs de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="ffb74-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="ffb74-106">Ouvrez ADSI Edit : Cliquez sur **Démarrer**, sur **Outils d’administration**, puis cliquez sur **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="ffb74-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ffb74-107">Sinon, cliquez sur **Démarrer**, puis sur **exécuter**, type **adsiedit.msc** pour démarrer l’utilitaire de modification ADSI.</span><span class="sxs-lookup"><span data-stu-id="ffb74-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="ffb74-108">Dans l’arborescence de la Console de gestion Microsoft (MMC), s’il n’est pas déjà sélectionné, cliquez sur ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="ffb74-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="ffb74-109">Dans le menu **Action**, cliquez sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="ffb74-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="ffb74-110">Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffb74-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="ffb74-111">Sous le conteneur schéma, recherchez CN = ms-RTC-SIP-version de schéma.</span><span class="sxs-lookup"><span data-stu-id="ffb74-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="ffb74-112">Si cet objet existe et la valeur de l’attribut **rangeUpper** est 1150 et la valeur de l’attribut **rangeLower** a la valeur 3, puis le schéma a été correctement mis à jour et répliqué.</span><span class="sxs-lookup"><span data-stu-id="ffb74-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="ffb74-113">Si cet objet n’existe pas ou si les valeurs des attributs **rangeUpper** et **rangeLower** ne sont pas spécifiés, puis le schéma n’a pas été modifié ou n’a pas répliqué.</span><span class="sxs-lookup"><span data-stu-id="ffb74-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ffb74-114">Si votre contrôle de la réplication du schéma ne s’affiche pas encore une réplication réussie, attendez 15 minutes environ, puis vérifiez à nouveau.</span><span class="sxs-lookup"><span data-stu-id="ffb74-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="ffb74-115">La réplication Active Directory est basée sur un modèle de cohérence et une latence de réplication peut se produire, basée sur un certain nombre de facteurs dans le serveur et l’infrastructure.</span><span class="sxs-lookup"><span data-stu-id="ffb74-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

