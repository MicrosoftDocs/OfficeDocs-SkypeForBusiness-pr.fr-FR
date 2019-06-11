---
title: Test des adresses postales par rapport au guide principal des adresses
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa4dd28ec05546366e029b6fb9fdf1c4b3ae310
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="74eef-102">Test des adresses postales par rapport au Guide d’adresses principal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74eef-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74eef-103">_**Dernière modification de la rubrique:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="74eef-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74eef-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="74eef-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="74eef-105">Jour</span><span class="sxs-lookup"><span data-stu-id="74eef-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74eef-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="74eef-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="74eef-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74eef-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74eef-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="74eef-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="74eef-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="74eef-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="74eef-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="74eef-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="74eef-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="74eef-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="74eef-112">Description</span><span class="sxs-lookup"><span data-stu-id="74eef-112">Description</span></span>

<span data-ttu-id="74eef-113">L’applet de contrôle test-CsLisCivicAddress est utilisée pour vérifier les emplacements qui ont été ajoutés à votre base de données de service d’information d’emplacement (LIS).</span><span class="sxs-lookup"><span data-stu-id="74eef-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="74eef-114">L’applet de contrôle fonctionne en comparant les emplacements figurant dans le Guide de l’adresse principale (MSAG), qui appartient à votre fournisseur de routage réseau E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="74eef-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="74eef-115">Si vous n’avez pas de fournisseur de routage réseau ou si le fournisseur ne peut pas être atteint, vos tests échoueront.</span><span class="sxs-lookup"><span data-stu-id="74eef-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="74eef-116">Si vous ajoutez le paramètre de commutateur UpdateValidationStatus à votre commande, la propriété de base de données MSAGValid correspondante sera définie sur true pour chaque adresse passant le test.</span><span class="sxs-lookup"><span data-stu-id="74eef-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="74eef-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="74eef-117">Running the test</span></span>

<span data-ttu-id="74eef-118">L’applet de contrôle test-CsLisCivicAddress peut être utilisée pour tester des adresses individuelles ou pour tester plusieurs adresses.</span><span class="sxs-lookup"><span data-stu-id="74eef-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="74eef-119">Par exemple, la commande suivante teste une adresse unique située dans Redmond, WA:</span><span class="sxs-lookup"><span data-stu-id="74eef-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="74eef-120">Par comparaison, cette commande teste toutes les adresses figurant actuellement dans votre base de données LIS:</span><span class="sxs-lookup"><span data-stu-id="74eef-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="74eef-121">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="74eef-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="74eef-122">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="74eef-122">Determining success or failure</span></span>

<span data-ttu-id="74eef-123">Test-CsLisCivicAddress rapportera la réussite ou l’échec pour les adresses fournies.</span><span class="sxs-lookup"><span data-stu-id="74eef-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="74eef-124">Un test d’adresse échoue si l’adresse est introuvable ou si le fournisseur de services ne peut pas être contacté.</span><span class="sxs-lookup"><span data-stu-id="74eef-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="74eef-125">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="74eef-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="74eef-126">Voici quelques raisons courantes pour lesquelles les tests-CsLisCivicAddress peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="74eef-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="74eef-127">Le fournisseur de service LIS n’est peut-être pas disponible.</span><span class="sxs-lookup"><span data-stu-id="74eef-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="74eef-128">Vous pouvez récupérer l’URL de votre fournisseur de services LIS en exécutant l’applet de recherche Get-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="74eef-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="74eef-129">Vous pouvez alors exécuter une commande ping sur cette URL pour vérifier que le fournisseur de services est disponible.</span><span class="sxs-lookup"><span data-stu-id="74eef-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

