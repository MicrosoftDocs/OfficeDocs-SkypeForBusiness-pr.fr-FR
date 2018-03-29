---
title: Configuration du magasin de contacts personnels sur les ordinateurs client pour Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Résumé : Configurer le magasin de contacts personnel utilisé par Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server 2015.'
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a><span data-ttu-id="cb517-103">Configuration du magasin de contacts personnels sur les ordinateurs client pour Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="cb517-103">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="cb517-104">**Résumé :** Configurer le magasin de contacts personnel utilisé par Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cb517-104">**Summary:** Configure the personal contact store used by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="cb517-105">Si vous intégrez Skype pour Business Server 2015 et 2016 d’Exchange Server ou Exchange Server 2013, vous devez configurer le magasin de contacts personnel sur les ordinateurs client Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="cb517-105">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store on any client computers running Skype for Business.</span></span> <span data-ttu-id="cb517-106">En particulier, vous devez configurer Skype pour entreprises utilisent Exchange comme le magasin de contacts personnel, et, en même temps, assurez-vous que les utilisateurs ne sont pas en mesure de passer outre cette décision.</span><span class="sxs-lookup"><span data-stu-id="cb517-106">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="cb517-107">Vous pouvez faire cela en créant et en configurant une valeur Registre sur chaque ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="cb517-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
<span data-ttu-id="cb517-108">Notez que cela n’est pas requis sur les ordinateurs exécutant Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="cb517-108">Note that this is not required on computers running Skype for Business.</span></span>
  
<span data-ttu-id="cb517-109">Pour configurer cette valeur sur un ordinateur unique, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cb517-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="cb517-110">Sur l’ordinateur client, cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="cb517-110">On the client computer, click **Start** and then click **Run**.</span></span>
    
2. <span data-ttu-id="cb517-111">Dans la boîte de dialogue **Exécuter** tapez regedit, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="cb517-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
    
3. <span data-ttu-id="cb517-112">Dans l’Éditeur du Registre, développez **HKEY_LOCAL_MACHINE**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="cb517-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
    
4. <span data-ttu-id="cb517-113">Cliquez avec le bouton droit sur **Communicator**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="cb517-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
    
5. <span data-ttu-id="cb517-114">Après création de la nouvelle valeur, tapez PersonalContactStoreOverride et appuyez sur ENTRÉE pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="cb517-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
    
6. <span data-ttu-id="cb517-115">Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.</span><span class="sxs-lookup"><span data-stu-id="cb517-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>
    
<span data-ttu-id="cb517-116">Si vous devez effectuer le même changement sur plusieurs ordinateurs, vous pouvez le faire en créant un objet Stratégie de groupe personnalisé.</span><span class="sxs-lookup"><span data-stu-id="cb517-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="cb517-117">Pour plus d’informations, consultez la documentation de la stratégie de groupe à [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span><span class="sxs-lookup"><span data-stu-id="cb517-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span></span>
  

