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
ms.openlocfilehash: fca31c97e0d059cda9f6b39a0e17e8350a37cf52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a>Ajouter un Survivable Branch appliance à Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-23_

Si vous envisagez de déployer un Survivable Branch appliance, vous devez ajouter le Survivable Branch Appliance aux services de domaine Active Directory. Cette procédure doit être effectuée sur le site central.

<div>


> [!IMPORTANT]  
> Effectuez cette procédure uniquement si vous déployez un Survivable Branch appliance. Ne l’exécutez pas si vous déployez un serveur Survivable Branch Server.



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a>Pour ajouter un Survivable Branch Appliance aux services de domaine Active Directory

1.  Ouvrez une session sur un serveur membre, en tant que membre du groupe Administrateurs d’entreprise.

2.  Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Utilisateurs et ordinateurs Active Directory**.

3.  Dans le menu **Actions**, cliquez sur **Nouveau**, puis sur **Ordinateur**.

4.  Dans la boîte de dialogue **nouvel objet-ordinateur** , tapez un nom pour l’objet de l’ordinateur Survivable Branch Appliance (par exemple, BranchOffice1), puis cliquez sur **modifier**.

5.  Dans la boîte de dialogue **Sélectionner un utilisateur ou un groupe**, ajoutez le groupe RTCUniversalSBATechnicians, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Un membre du groupe RTCUniversalSBATechnicians sur le site de succursale ajoutera ce périphérique au domaine plus tard.

    
    </div>

6.  Cliquez sur **OK** pour enregistrer l’objet Survivable Branch appliance.

7.  Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Modification ADSI**.

8.  Dans **Modification ADSI**, cliquez avec le bouton droit sur l’objet ordinateur que vous avez créé au cours des étapes précédentes, puis cliquez sur **Propriétés**.

9.  Dans la liste d’attributs, cliquez sur **servicePrincipalName**, puis sur **Modifier**.

10. Dans le champ **valeur à ajouter** , tapez nom de\<domaine complet\> hôte \</SBA\> où le nom de domaine complet SBA est le nom de domaine complet (FQDN) de votre Survivable Branch appliance. Par exemple, tapez **HOST/SiteSuccursale1.contoso.com**.

11. Cliquez sur **OK** pour enregistrer le paramètre d’attribut **servicePrincipalName**, puis cliquez sur **OK** pour enregistrer les propriétés de l’objet ordinateur.

12. Dans **Utilisateurs et ordinateurs Active Directory**, cliquez avec le bouton droit sur **Utilisateurs**, cliquez sur **Nouveau**, puis sur **Utilisateur**.

13. Entrez les informations dans l’Assistant pour créer un compte d’utilisateur de domaine pour un technicien Survivable Branch appliance.

14. Dans **Utilisateurs et ordinateurs Active Directory**, cliquez sur **Utilisateurs**, cliquez avec le bouton droit de la souris sur l’objet utilisateur, puis sur **Ajouter à un groupe**.

15. Dans **Entrez les noms d’objets à sélectionner**, tapez **RTCUniversalSBATechnicians**, puis cliquez sur **OK**.

16. Répétez les étapes 12 à 15 pour chaque technicien de site de succursale.

**Étape suivante**: [Ajouter des sites de succursale à votre topologie dans Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

