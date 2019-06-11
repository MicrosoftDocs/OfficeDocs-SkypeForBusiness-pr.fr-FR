---
title: 'Lync Server 2013 : Ajout d’un Survivable Branch Appliance à Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc057318a0d241a28b8529802ea9f2016a1f5b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Ajout d’un Survivable Branch Appliance à Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-23_

Si vous envisagez de déployer une application de succursale Survivable, vous devez ajouter l’unité de branchement survivant aux services de domaine Active Directory (AD FS). Suivez cette procédure sur le site central.

<div>


> [!IMPORTANT]  
> Procédez comme suit uniquement si vous déployez une application de succursale Survivable. Ne l’exécutez pas si vous déployez un serveur de succursales survivant.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Pour ajouter une unité de branchement survivant aux services de domaine Active Directory (AD FS)

1.  Connectez-vous à un serveur membre en tant que membre du groupe administrateurs d’entreprise.

2.  Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **utilisateurs et ordinateurs Active Directory**.

3.  Dans le menu **actions** , cliquez sur **nouveau** , puis sur **ordinateur**.

4.  Dans la boîte de dialogue **nouvel objet-ordinateur** , tapez un nom pour l’objet de l’unité de branchement Survivable (par exemple, BranchOffice1), puis cliquez sur **modifier**.

5.  Dans la boîte de dialogue **Sélectionner un utilisateur ou un groupe** , ajoutez le groupe RTCUniversalSBATechnicians, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Un membre du groupe RTCUniversalSBATechnicians sur le site de succursale ajoutera cet appareil au domaine ultérieurement.

    
    </div>

6.  Cliquez sur **OK** pour enregistrer l’objet de l’unité de branchement Survivable.

7.  Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **modification ADSI**.

8.  Dans **modification ADSI**, cliquez avec le bouton droit sur l’objet ordinateur que vous avez créé au cours des étapes précédentes, puis cliquez sur **Propriétés**.

9.  Dans la liste des attributs, cliquez sur **servicePrincipalName**, puis cliquez sur **modifier**.

10. Dans le champ **valeur à ajouter** , tapez nom de\<domaine complet\> host \</SBA\> où le FQDN est le nom de domaine complet (FQDN) de votre appareil de branchement Survivable. Par exemple, tapez **Host/BranchOffice1. contoso. com**.

11. Cliquez sur **OK** pour enregistrer les paramètres d’attribut **servicePrincipalName** , puis cliquez sur **OK** pour enregistrer les propriétés de l’objet ordinateur.

12. Dans **utilisateurs et ordinateurs Active Directory**, cliquez avec le bouton droit sur **utilisateurs**, cliquez sur **nouveau**, puis sur **utilisateur**.

13. Entrez les informations dans l’Assistant pour créer un compte d’utilisateur de domaine pour un technicien d’appareil de succursale Survivable.

14. Dans **utilisateurs et ordinateurs Active Directory**, cliquez sur **utilisateurs**, cliquez avec le bouton droit sur l’objet utilisateur, puis cliquez sur **Ajouter à un groupe**.

15. Dans **Entrez les noms des objets à sélectionner**, tapez **RTCUniversalSBATechnicians**, puis cliquez sur **OK**.

16. Répétez les étapes 12-15 pour chaque technicien de site de succursale.

**Étape suivante**: [Ajouter des sites de succursale à votre topologie dans Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

