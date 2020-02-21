---
title: 'Lync Server 2013 : ajout d’un Survivable Branch appliance à Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25d8efb03b4d67b6409f93b6a99d2314cb703952
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="ba1e4-102">Ajouter un Survivable Branch appliance à Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba1e4-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba1e4-103">_**Dernière modification de la rubrique :** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="ba1e4-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="ba1e4-104">Si vous envisagez de déployer un Survivable Branch appliance, vous devez ajouter le Survivable Branch Appliance aux services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="ba1e4-105">Cette procédure doit être effectuée sur le site central.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ba1e4-106">Effectuez cette procédure uniquement si vous déployez un Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="ba1e4-107">Ne l’exécutez pas si vous déployez un serveur Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="ba1e4-108">Pour ajouter un Survivable Branch Appliance aux services de domaine Active Directory</span><span class="sxs-lookup"><span data-stu-id="ba1e4-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="ba1e4-109">Ouvrez une session sur un serveur membre, en tant que membre du groupe Administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="ba1e4-110">Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Utilisateurs et ordinateurs Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="ba1e4-111">Dans le menu **Actions**, cliquez sur **Nouveau**, puis sur **Ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="ba1e4-112">Dans la boîte de dialogue **nouvel objet-ordinateur** , tapez un nom pour l’objet de l’ordinateur Survivable Branch Appliance (par exemple, BranchOffice1), puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="ba1e4-113">Dans la boîte de dialogue **Sélectionner un utilisateur ou un groupe**, ajoutez le groupe RTCUniversalSBATechnicians, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ba1e4-114">Un membre du groupe RTCUniversalSBATechnicians sur le site de succursale ajoutera ce périphérique au domaine plus tard.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="ba1e4-115">Cliquez sur **OK** pour enregistrer l’objet Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="ba1e4-116">Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Modification ADSI**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="ba1e4-117">Dans **Modification ADSI**, cliquez avec le bouton droit sur l’objet ordinateur que vous avez créé au cours des étapes précédentes, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="ba1e4-118">Dans la liste d’attributs, cliquez sur **servicePrincipalName**, puis sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="ba1e4-119">Dans le champ **valeur à ajouter** , tapez nom de\<domaine complet\> hôte \</SBA\> où le nom de domaine complet SBA est le nom de domaine complet (FQDN) de votre Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="ba1e4-120">Par exemple, tapez **HOST/SiteSuccursale1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="ba1e4-121">Cliquez sur **OK** pour enregistrer le paramètre d’attribut **servicePrincipalName**, puis cliquez sur **OK** pour enregistrer les propriétés de l’objet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="ba1e4-122">Dans **Utilisateurs et ordinateurs Active Directory**, cliquez avec le bouton droit sur **Utilisateurs**, cliquez sur **Nouveau**, puis sur **Utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="ba1e4-123">Entrez les informations dans l’Assistant pour créer un compte d’utilisateur de domaine pour un technicien Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="ba1e4-124">Dans **Utilisateurs et ordinateurs Active Directory**, cliquez sur **Utilisateurs**, cliquez avec le bouton droit de la souris sur l’objet utilisateur, puis sur **Ajouter à un groupe**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="ba1e4-125">Dans **Entrez les noms d’objets à sélectionner**, tapez **RTCUniversalSBATechnicians**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="ba1e4-126">Répétez les étapes 12 à 15 pour chaque technicien de site de succursale.</span><span class="sxs-lookup"><span data-stu-id="ba1e4-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="ba1e4-127">**Étape suivante**: [Ajouter des sites de succursale à votre topologie dans Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="ba1e4-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

