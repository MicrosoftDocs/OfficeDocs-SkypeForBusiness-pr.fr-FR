---
title: Configurer le magasin de contacts personnels sur les ordinateurs clients Lync 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Résumé : Configurez le magasin de contacts personnels utilisé par les clients hérités.'
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833934"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="9534c-103">Configurer le magasin de contacts personnels sur les ordinateurs clients Lync 2010</span><span class="sxs-lookup"><span data-stu-id="9534c-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="9534c-104">Si vous intégrez Skype Entreprise Server 2015 et Exchange Server 2016 ou Exchange Server 2013, vous devez configurer le magasin de contacts personnels utilisé par les clients.</span><span class="sxs-lookup"><span data-stu-id="9534c-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="9534c-105">En particulier, vous devez configurer Skype Entreprise pour utiliser Exchange comme magasin de contacts personnels et, en même temps, vous assurer que les utilisateurs ne sont pas en mesure de remplacer cette décision.</span><span class="sxs-lookup"><span data-stu-id="9534c-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="9534c-106">Pour ce faire, vous pouvez créer et configurer une valeur de Registre sur chaque ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="9534c-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9534c-107">La procédure suivante est uniquement nécessaire pour les clients qui utilisent le client Lync 2010 ou une antérieure.</span><span class="sxs-lookup"><span data-stu-id="9534c-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="9534c-108">Le client Lync 2013 et tous les clients Skype Entreprise n’auront pas la possibilité de remplacement des paramètres du magasin de contacts.</span><span class="sxs-lookup"><span data-stu-id="9534c-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="9534c-109">Pour configurer cette valeur sur un seul ordinateur, complétez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="9534c-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="9534c-110">Sur l’ordinateur client, cliquez sur **Démarrer,** puis sur **Exécuter.**</span><span class="sxs-lookup"><span data-stu-id="9534c-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="9534c-111">Dans la boîte de dialogue **Exécuter**, tapez regedit, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="9534c-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="9534c-112">Dans l’Éditeur du Registre, **développez HKEY_LOCAL_MACHINE,** développez **logiciel,** développez **Stratégies,** **développez Microsoft,** puis développez **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="9534c-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="9534c-113">Cliquez avec le **bouton Communicator**, pointez sur **Nouveau,** puis cliquez sur **Valeur DWORD (32 bits).**</span><span class="sxs-lookup"><span data-stu-id="9534c-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="9534c-114">Une fois la nouvelle valeur créée, tapez PersonalContactStoreOverride, puis appuyez sur Entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="9534c-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="9534c-115">Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.</span><span class="sxs-lookup"><span data-stu-id="9534c-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="9534c-116">Si vous devez apporter la même modification sur plusieurs ordinateurs, vous pouvez le faire en créant un objet de stratégie de groupe personnalisé.</span><span class="sxs-lookup"><span data-stu-id="9534c-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="9534c-117">Pour plus d’informations sur cette situation dans Windows 10, voir l’article Créer un objet [de stratégie de groupe.](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="9534c-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
