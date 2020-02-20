---
title: 'Lync Server 2013 : définition d’un mot de passe de compte d’authentification Kerberos sur un serveur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeef318392540aaa0600a4b61f20a296df25ca5f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="84fef-102">Définir un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84fef-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84fef-103">_**Dernière modification de la rubrique :** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="84fef-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="84fef-104">Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="84fef-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="84fef-105">Vous devez configurer un mot de passe sur le compte Kerberos pour chaque site disposant de serveurs frontaux, de serveurs Standard Edition et de directeurs.</span><span class="sxs-lookup"><span data-stu-id="84fef-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="84fef-106">Vous pouvez configurer le mot de passe en exécutant l’applet de commande Windows PowerShell **Set-CsKerberosAccountPassword** sur un serveur du site (par exemple, un serveur frontal).</span><span class="sxs-lookup"><span data-stu-id="84fef-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="84fef-107">Pour chaque site, vous devez exécuter l’applet de commande **Set-CsKerberosAccountPassword** .</span><span class="sxs-lookup"><span data-stu-id="84fef-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="84fef-108">L’applet de commande configure Internet Information Services (IIS) pour le service Web, puis définit le mot de passe sur le compte d’ordinateur dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="84fef-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="84fef-109">Une autre méthode, basée sur le type de paramètre utilisé dans l’applet de commande, configure IIS sur un serveur tout en utilisant un autre serveur ayant été configuré comme source du mot de passe du compte Kerberos.</span><span class="sxs-lookup"><span data-stu-id="84fef-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="84fef-110">Lorsque vous utilisez l’applet de commande **Set-CsKerberosAccountPassword** pour définir un mot de passe, Kerberos définit le mot de passe en tant que chaîne générée de manière aléatoire.</span><span class="sxs-lookup"><span data-stu-id="84fef-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="84fef-111">Cette applet de commande contacte toutes les instances IIS de tous les sites Lync Server 2013 centraux auxquels ce compte est affecté.</span><span class="sxs-lookup"><span data-stu-id="84fef-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="84fef-112">Pour définir un mot de passe de compte d’authentification Kerberos</span><span class="sxs-lookup"><span data-stu-id="84fef-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="84fef-113">Ouvrez une session sur un ordinateur du domaine sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="84fef-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="84fef-114">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="84fef-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="84fef-115">Depuis la ligne de commande, exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="84fef-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="84fef-116">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="84fef-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="84fef-p103">Vous devez spécifier le paramètre Compte d’utilisateur au format Domaine\Utilisateur. Le format Utilisateur@Domaine.extension n’est pas pris en charge pour le référencement des objets Ordinateur créés à des fins d’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="84fef-p103">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="84fef-119">Après avoir apporté des modifications à l’authentification Kerberos, telles que l’ajout d’un compte ou la suppression d’un compte, vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="84fef-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

