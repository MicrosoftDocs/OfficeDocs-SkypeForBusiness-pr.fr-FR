---
title: Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e71f87c20064e542aa6a8db1d9b38048c5f736
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="7bd22-102">Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7bd22-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bd22-103">_**Dernière modification de la rubrique :** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="7bd22-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="7bd22-104">Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7bd22-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="7bd22-105">Dans un site, des serveurs frontaux, des serveurs Standard Edition et des directeurs peuvent utiliser un compte d’authentification Kerberos dans le but d’authentifier les demandes envoyées au service de services Web.</span><span class="sxs-lookup"><span data-stu-id="7bd22-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="7bd22-106">Cette procédure recherche sur chaque serveur exécutant des services Web dans un site qui a été affecté un compte Kerberos et met à jour les paramètres de configuration d’Internet Information Services (IIS) pour utiliser le compte Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7bd22-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="7bd22-107">Pour plus d’informations, consultez [définir un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span><span class="sxs-lookup"><span data-stu-id="7bd22-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="7bd22-108">Pour définir et configurer un mot de passe de compte d’authentification Kerberos</span><span class="sxs-lookup"><span data-stu-id="7bd22-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="7bd22-109">Connectez-vous à un ordinateur source (tel que fe01.contoso.com) en tant que membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7bd22-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="7bd22-110">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7bd22-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7bd22-111">À partir de la ligne de commande Lync Server Management Shell, exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7bd22-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="7bd22-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="7bd22-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="7bd22-113">Le nom de l’ordinateur source et de l’ordinateur de destination doit être un nom de domaine complet (FQDN) du serveur.</span><span class="sxs-lookup"><span data-stu-id="7bd22-113">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server.</span></span> <span data-ttu-id="7bd22-114">Vous ne pouvez pas utiliser le nom de domaine complet (FQDN) du pool, sauf s’il est identique à celui de l’ordinateur que vous utilisez en tant qu’ordinateur source ou ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="7bd22-114">You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="7bd22-115">Après avoir apporté des modifications à l’authentification Kerberos (par exemple, ajout d’un compte ou suppression d’un compte), vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7bd22-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

