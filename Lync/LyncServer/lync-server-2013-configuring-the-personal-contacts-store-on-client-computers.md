---
title: 'Lync Server 2013 : configuration du magasin de contacts personnels sur les ordinateurs clients'
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
ms.openlocfilehash: 6020182c0083ecadcb65c07fa71be213f9458f0f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532341"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="eebee-102">Configuration du magasin de contacts personnels sur les ordinateurs clients pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eebee-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eebee-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="eebee-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="eebee-104">Si vous intégrez Microsoft Lync Server 2013 et Microsoft Exchange Server 2013, il est recommandé de configurer le magasin de contacts personnels sur les ordinateurs clients exécutant Microsoft Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="eebee-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="eebee-105">En particulier, vous devez configurer Lync pour qu’il utilise Exchange comme magasin de contacts personnel et, en même temps, vérifier que les utilisateurs ne sont pas en mesure de remplacer cette décision.</span><span class="sxs-lookup"><span data-stu-id="eebee-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="eebee-106">Cette opération peut être réalisée en créant et en configurant une valeur de Registre sur chaque ordinateur client.</span><span class="sxs-lookup"><span data-stu-id="eebee-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="eebee-107">Notez que cette fonction n’est pas obligatoire sur les ordinateurs exécutant Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="eebee-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="eebee-108">Pour configurer cette valeur sur un seul ordinateur, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="eebee-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="eebee-109">Sur l’ordinateur client, cliquez sur **Démarrer** , puis sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="eebee-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="eebee-110">Dans la boîte de dialogue **Exécuter**, tapez regedit, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="eebee-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="eebee-111">Dans l’éditeur du Registre, développez **HKEY \_ local \_ machine**, **Software**, **Policies**, **Microsoft**, puis **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="eebee-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="eebee-112">Cliquez avec le bouton droit sur **Communicator**, pointez sur **nouveau**, puis cliquez sur **valeur DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="eebee-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="eebee-113">Une fois la nouvelle valeur créée, tapez **PersonalContactStoreOverride** , puis appuyez sur entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="eebee-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="eebee-114">Vérifiez que la valeur de PersonalContactStoreOverride est définie sur 0, puis fermez l’éditeur du Registre.</span><span class="sxs-lookup"><span data-stu-id="eebee-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="eebee-115">Si vous devez effectuer cette même modification sur plusieurs ordinateurs, vous pouvez le faire en créant un objet de stratégie de groupe personnalisé.</span><span class="sxs-lookup"><span data-stu-id="eebee-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="eebee-116">Pour plus d’informations, consultez la documentation sur la stratégie de groupe à l’adresse [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) .</span><span class="sxs-lookup"><span data-stu-id="eebee-116">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

