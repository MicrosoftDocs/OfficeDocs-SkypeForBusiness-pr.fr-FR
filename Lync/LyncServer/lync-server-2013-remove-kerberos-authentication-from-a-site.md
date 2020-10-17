---
title: 'Lync Server 2013 : suppression de l’authentification Kerberos d’un site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7fdf5a304d428efb3b1192d02ade0187f052171
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536411"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="4df13-102">Dans Lync Server 2013, supprimez l’authentification Kerberos d’un site.</span><span class="sxs-lookup"><span data-stu-id="4df13-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4df13-103">_**Dernière modification de la rubrique :** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="4df13-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="4df13-104">Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4df13-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="4df13-105">Si vous devez supprimer l’authentification Kerberos d’un site ou supprimer un site, vous devez supprimer l’affectation du compte d’authentification Kerberos du site à l’aide de l’applet de commande **Remove-CsKerberosAccountAssignment**.</span><span class="sxs-lookup"><span data-stu-id="4df13-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="4df13-106">Utilisez la procédure suivante pour supprimer l’affectation du compte d’authentification Kerberos, ce qui a pour effet de supprimer l’affectation de tous les ordinateurs présents sur le site.</span><span class="sxs-lookup"><span data-stu-id="4df13-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="4df13-107">Si vous supprimez définitivement le compte Kerberos, utilisez utilisateurs et ordinateurs Active Directory pour le supprimer des services de domaine Active Directory après avoir supprimé l’attribution.</span><span class="sxs-lookup"><span data-stu-id="4df13-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="4df13-108">Si vous envisagez d’utiliser l’objet ultérieurement, vous pouvez peut-être conserver l’objet Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4df13-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="4df13-109">Pour supprimer l’authentification Kerberos d’un site</span><span class="sxs-lookup"><span data-stu-id="4df13-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="4df13-110">En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="4df13-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="4df13-111">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4df13-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4df13-112">Depuis la ligne de commande, exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="4df13-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="4df13-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4df13-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4df13-114">Après avoir apporté des modifications à l’authentification Kerberos, telles que l’ajout d’un compte ou la suppression d’un compte, vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4df13-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

