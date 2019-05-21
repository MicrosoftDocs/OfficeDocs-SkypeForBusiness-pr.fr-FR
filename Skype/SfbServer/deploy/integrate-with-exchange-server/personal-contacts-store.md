---
title: Configurer le magasin de contacts personnels sur les ordinateurs clients Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Résumé: configurez le magasin de contacts personnel utilisé par les clients hérités.'
ms.openlocfilehash: ba9cb7ee485f94162a642f8e877213a7bcd47c55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278083"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="450df-103">Configurer le magasin de contacts personnels sur les ordinateurs clients Lync 2010</span><span class="sxs-lookup"><span data-stu-id="450df-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="450df-104">Si vous intégrez Skype entreprise Server 2015 et Exchange Server 2016 ou Exchange Server 2013, vous devez configurer le magasin de contacts personnel utilisé par les clients.</span><span class="sxs-lookup"><span data-stu-id="450df-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="450df-105">Par exemple, vous devez configurer Skype entreprise pour qu’il utilise Exchange comme magasin de contacts personnel et, en même temps, veiller à ce que les utilisateurs ne puissent pas ignorer cette décision.</span><span class="sxs-lookup"><span data-stu-id="450df-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="450df-106">Vous pouvez faire cela en créant et en configurant une valeur Registre sur chaque ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="450df-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="450df-107">La procédure suivante est uniquement nécessaire pour les clients qui utilisent le client Lync 2010 ou une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="450df-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="450df-108">Le client Lync 2013 et tous les clients Skype entreprise n’ont pas la possibilité de remplacer les paramètres du magasin de contacts.</span><span class="sxs-lookup"><span data-stu-id="450df-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="450df-109">Pour configurer cette valeur sur un ordinateur unique, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="450df-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="450df-110">Sur l’ordinateur client, cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="450df-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="450df-111">Dans la boîte de dialogue **Exécuter** tapez regedit, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="450df-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="450df-112">Dans l’Éditeur du Registre, développez **HKEY_LOCAL_MACHINE**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="450df-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="450df-113">Cliquez avec le bouton droit sur **Communicator**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="450df-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="450df-114">Une fois la nouvelle valeur créée, tapez PersonalContactStoreOverride, puis appuyez sur Entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="450df-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="450df-115">Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.</span><span class="sxs-lookup"><span data-stu-id="450df-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="450df-116">Si vous devez effectuer le même changement sur plusieurs ordinateurs, vous pouvez le faire en créant un objet Stratégie de groupe personnalisé.</span><span class="sxs-lookup"><span data-stu-id="450df-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="450df-117">Pour en savoir plus sur Windows 10, voir l’article [créer un objet de stratégie de groupe](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .</span><span class="sxs-lookup"><span data-stu-id="450df-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
