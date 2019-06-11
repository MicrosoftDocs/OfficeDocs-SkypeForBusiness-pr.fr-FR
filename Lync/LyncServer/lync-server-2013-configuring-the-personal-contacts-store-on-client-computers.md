---
title: 'Lync Server 2013: configuration du magasin de contacts personnels sur les ordinateurs clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4f9b7bbb50b5e63e87904d29a01715fcdcac8c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="058cb-102">Configuration du magasin de contacts personnels sur les ordinateurs clients pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="058cb-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="058cb-103">_**Dernière modification de la rubrique:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="058cb-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="058cb-104">Si vous intégrez Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, il est recommandé de configurer le magasin de contacts personnels sur les ordinateurs clients exécutant Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="058cb-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="058cb-105">En particulier, vous devez configurer Lync pour qu’il utilise Exchange en tant que magasin de contacts personnel et, en même temps, veiller à ce que les utilisateurs ne puissent pas ignorer cette décision.</span><span class="sxs-lookup"><span data-stu-id="058cb-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="058cb-106">Vous pouvez faire cela en créant et en configurant une valeur Registre sur chaque ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="058cb-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="058cb-107">Notez que cela n’est pas requis sur les ordinateurs exécutant Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="058cb-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="058cb-108">Pour configurer cette valeur sur un ordinateur unique, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="058cb-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="058cb-109">Sur l’ordinateur client, cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="058cb-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="058cb-110">Dans la boîte de dialogue **Exécuter** tapez regedit, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="058cb-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="058cb-111">Dans l’éditeur du Registre, développez l' **application** **HKEY\_local\_**, développez logiciel, développez **stratégies**, développez **Microsoft**, puis développez **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="058cb-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="058cb-112">Cliquez avec le bouton droit sur **Communicator**, pointez sur **Nouveau**, puis cliquez sur **Valeur DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="058cb-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="058cb-113">Une fois la nouvelle valeur créée, tapez **PersonalContactStoreOverride**, puis appuyez sur Entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="058cb-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="058cb-114">Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’Éditeur du Registre.</span><span class="sxs-lookup"><span data-stu-id="058cb-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="058cb-115">Si vous devez effectuer le même changement sur plusieurs ordinateurs, vous pouvez le faire en créant un objet Stratégie de groupe personnalisé.</span><span class="sxs-lookup"><span data-stu-id="058cb-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="058cb-116">Pour plus d’informations, consultez la documentation relative [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)à la stratégie de groupe à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="058cb-116">For details, see the Group Policy documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

