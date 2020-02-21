---
title: 'Lync Server 2013 : attribution d’un compte d’authentification Kerberos à un site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a28efed0276fd1665746f55fdf2bdc14cef8e226
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="a2ec4-102">Affecter un compte d’authentification Kerberos à un site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2ec4-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2ec4-103">_**Dernière modification de la rubrique :** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="a2ec4-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="a2ec4-104">Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="a2ec4-105">Après avoir créé le compte Kerberos, vous devez l’assigner à un site.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="a2ec4-106">Il s’agit d’un site Lync Server 2013 et non d’un site Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="a2ec4-107">Vous pouvez créer plusieurs comptes d’authentification Kerberos par déploiement, mais vous ne pouvez assigner qu’un seul compte à un site.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="a2ec4-108">Pour assigner un compte d’authentification Kerberos existant à un site, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="a2ec4-109">Pour plus d’informations sur la création du compte Kerberos, voir [créer un compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="a2ec4-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="a2ec4-110">Pour assigne un compte d’authentification Kerberos à un site</span><span class="sxs-lookup"><span data-stu-id="a2ec4-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="a2ec4-111">En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="a2ec4-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a2ec4-113">Depuis la ligne de commande, exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a2ec4-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="a2ec4-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a2ec4-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="a2ec4-p102">Vous devez spécifier le paramètre Compte d’utilisateur au format Domaine\Utilisateur. Le format Utilisateur@Domaine.extension n’est pas pris en charge pour la référence aux objets créés à des fins d’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-p102">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="a2ec4-117">**Facultatif**: vous avez peut-être configuré un nom de domaine complet (FQDN) de remplacement pour vos WebServices, en fonction de [la modification de l’URL des services Web dans Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="a2ec4-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="a2ec4-118">Si c’est le cas, vous devrez également ajouter un SPN pour ce nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="a2ec4-119">Par exemple, si le nom de domaine complet était WebServices. contoso. local, vous devez exécuter :</span><span class="sxs-lookup"><span data-stu-id="a2ec4-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a2ec4-120">Après avoir apporté des modifications à l’authentification Kerberos, telles que l’ajout d’un compte ou la suppression d’un compte, vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a2ec4-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

