---
title: Test de la configuration du compte Kerberos affecté à un site
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af595ff7a345f7309f832d76aaf033675755f8da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="bbb0e-102">Test de la configuration du compte Kerberos affecté à un site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbb0e-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbb0e-103">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="bbb0e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bbb0e-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="bbb0e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bbb0e-105">Tous les jours</span><span class="sxs-lookup"><span data-stu-id="bbb0e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bbb0e-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="bbb0e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bbb0e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbb0e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bbb0e-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="bbb0e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bbb0e-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bbb0e-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="bbb0e-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="bbb0e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bbb0e-112">Description</span><span class="sxs-lookup"><span data-stu-id="bbb0e-112">Description</span></span>

<span data-ttu-id="bbb0e-113">L’applet de commande test-CsKerberosAccountAssignment vous permet de vérifier qu’un compte Kerberos est associé à un site donné, que ce compte est configuré correctement et que le compte fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="bbb0e-114">Les comptes Kerberos sont des comptes d’ordinateur qui peuvent servir de principal d’authentification pour tous les ordinateurs d’un site qui exécutent Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="bbb0e-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="bbb0e-115">Étant donné que ces comptes utilisent le protocole d’authentification Kerberos, les comptes sont appelés comptes Kerberos et le nouveau processus d’authentification est appelé authentification Web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="bbb0e-116">Cela vous permet de gérer tous les serveurs IIS à l’aide d’un seul compte.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="bbb0e-117">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="bbb0e-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bbb0e-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="bbb0e-118">Running the Test</span></span>

<span data-ttu-id="bbb0e-119">Par défaut, test-CsKerberosAccountAssignment affiche une très petite sortie à l’écran.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="bbb0e-120">Au lieu de cela, les informations renvoyées par l’applet de commande sont écrites dans un fichier HTML.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="bbb0e-121">Pour cette raison, nous vous recommandons d’inclure le paramètre Verbose et le paramètre report à chaque fois que vous exécutez la commande test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="bbb0e-122">Le paramètre Verbose fournira une sortie plus détaillée à l’écran pendant l’exécution de l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="bbb0e-123">Le paramètre Report vous permet de spécifier un chemin d’accès et un nom de fichier pour le fichier HTML généré par test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="bbb0e-124">Si vous n’incluez pas le paramètre Report, le fichier HTML est automatiquement enregistré dans votre dossier Users et reçoit un nom semblable à celui-ci : ce84964a-c4da-4622-ad34-c54ff3ed361f. html.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="bbb0e-125">Vous devez également spécifier une identité de site lors de l’exécution de test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="bbb0e-126">Les comptes Kerberos sont attribués au niveau de l’étendue site.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="bbb0e-127">La commande suivante exécute test-CsKerberosAccountAssignment et enregistre la sortie dans un fichier nommé C :\\logs\\KerberosTest. html :</span><span class="sxs-lookup"><span data-stu-id="bbb0e-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="bbb0e-128">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="bbb0e-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bbb0e-129">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="bbb0e-129">Determining Success or Failure</span></span>

<span data-ttu-id="bbb0e-130">L’applet de commande test-CsKerberosAccountAssignment ne renvoie aucune indication simple de réussite ou d’échec.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="bbb0e-131">Au lieu de cela, vous devez afficher le fichier HTML généré à l’aide d’Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bbb0e-132">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="bbb0e-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="bbb0e-133">Voici quelques-unes des causes courantes de l’échec de test-CsKerberosAccountAssignment :</span><span class="sxs-lookup"><span data-stu-id="bbb0e-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="bbb0e-134">Vous avez peut-être spécifié une identité de site incorrecte.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="bbb0e-135">Pour renvoyer une liste d’identité de site valide, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="bbb0e-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="bbb0e-136">Une identité de site se présente généralement comme suit :</span><span class="sxs-lookup"><span data-stu-id="bbb0e-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="bbb0e-137">site : Redmond</span><span class="sxs-lookup"><span data-stu-id="bbb0e-137">site:Redmond</span></span>

  - <span data-ttu-id="bbb0e-138">Aucun compte Kerberos n’est affecté au site spécifié.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="bbb0e-139">Vous pouvez déterminer si un compte Kerberos est affecté à un site en exécutant une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="bbb0e-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="bbb0e-140">Votre compte Kerberos peut avoir un mot de passe qui n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="bbb0e-141">Si vous recevez le message d’erreur suivant dans le rapport, vous devrez probablement réinitialiser le mot de passe du compte Kerberos :</span><span class="sxs-lookup"><span data-stu-id="bbb0e-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="bbb0e-142">InvalidKerberosConfiguration : la configuration Kerberos n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="bbb0e-143">InvalidKerberosConfiguration : la configuration Kerberos sur atl-cs001.litwareinc.com n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="bbb0e-144">Le compte affecté attendu est litwareinc\\kerberostest.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="bbb0e-145">Assurez-vous que le compte n’a pas expiré et que le mot de passe configuré sur l’ordinateur correspond au mot de passe Active Directory du compte.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="bbb0e-146">Vous pouvez définir le mot de passe à l’aide de la cmdlet [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="bbb0e-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

