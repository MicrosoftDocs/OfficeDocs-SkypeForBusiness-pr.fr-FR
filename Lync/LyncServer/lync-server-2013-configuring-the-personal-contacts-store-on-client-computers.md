---
title: 'Lync Server 2013 : configuration du magasin de contacts personnels sur les ordinateurs clients'
description: 'Lync Server 2013 : configuration du magasin de contacts personnels sur les ordinateurs clients.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1040b3eb9aa38e3e0c537d690b9292ab8f1ead2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544190"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="8bcd1-103">Configuration du magasin de contacts personnels sur les ordinateurs clients pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bcd1-103">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bcd1-104">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="8bcd1-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="8bcd1-105">Si vous intégrez Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, il est recommandé de configurer le magasin de contacts personnels sur les ordinateurs clients exécutant Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-105">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="8bcd1-106">En particulier, vous devez configurer Lync pour qu’il utilise Exchange comme magasin de contacts personnel et, en même temps, vérifier que les utilisateurs ne sont pas en mesure de remplacer cette décision.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-106">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="8bcd1-107">Cette opération peut être réalisée en créant et en configurant une valeur de Registre sur chaque ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="8bcd1-108">Notez que cette fonction n’est pas obligatoire sur les ordinateurs exécutant Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-108">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="8bcd1-109">Pour configurer cette valeur sur un seul ordinateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="8bcd1-109">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="8bcd1-110">Sur l’ordinateur client, cliquez sur **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-110">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="8bcd1-111">Dans la boîte de dialogue **Exécuter**, tapez regedit, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="8bcd1-112">Dans l’éditeur du Registre, développez **HKEY \_ local \_ machine**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-112">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="8bcd1-113">Cliquez avec le bouton droit sur **Communicator**, pointez sur **nouveau**, puis cliquez sur **valeur DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="8bcd1-114">Une fois la nouvelle valeur créée, tapez **PersonalContactStoreOverride** , puis appuyez sur entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-114">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="8bcd1-115">Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’éditeur du Registre.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="8bcd1-116">Si vous devez effectuer cette même modification sur plusieurs ordinateurs, vous pouvez le faire en créant un objet de stratégie de groupe personnalisé.</span><span class="sxs-lookup"><span data-stu-id="8bcd1-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="8bcd1-117">Pour plus d’informations, consultez la documentation sur la stratégie de groupe à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) .</span><span class="sxs-lookup"><span data-stu-id="8bcd1-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

