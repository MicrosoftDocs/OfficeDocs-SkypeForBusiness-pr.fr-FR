---
title: 'Lync Server 2013 : Vue d’ensemble de la préparation des services de domaine Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26636846ce7b985a33af3175d51798c4c12c5ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Vue d’ensemble de la préparation des services de domaine Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-29_

Pour préparer les services de domaine Active Directory pour votre déploiement Lync Server 2013, vous devez effectuer trois étapes dans un ordre spécifique.

Le tableau suivant décrit les étapes nécessaires pour préparer AD DS pour Lync Server.

### <a name="active-directory-preparation-steps"></a>Étapes de préparation d’Active Directory

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Étape</th>
<th>Description</th>
<th>Où exécuter</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Préparation du schéma Active Directory dans Lync Server 2013</a></p></td>
<td><p>Étend le schéma Active Directory en ajoutant de nouvelles classes et attributs qui sont utilisés par Lync Server.</p>
<p>S’exécute une fois pour chaque forêt de votre déploiement où Lync Server sera déployé.</p></td>
<td><p>Par rapport au maître de schéma dans le domaine racine de chaque forêt pour le déploiement de Lync Server.</p>
<div>

> [!NOTE]  
> Vous n’avez pas besoin d’exécuter cette étape dans le domaine racine si vous disposez des autorisations requises sur le maître de schéma, mais vous devez être membre du groupe administrateurs d’entreprise dans le domaine racine et membre du groupe administrateurs d’entreprise sur le maître de schéma. Dans une topologie de forêt de ressources, exécutez cette étape uniquement dans la forêt de ressources, et non dans les forêts utilisateurs. Dans une topologie de forêt centrale, exécutez cette étape uniquement dans la forêt centrale et non dans les forêts utilisateurs.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Préparation de la forêt pour Lync Server 2013</a></p></td>
<td><p>Crée des paramètres globaux et des groupes universels utilisés par Lync Server.</p>
<p>S’exécute une fois pour chaque forêt de votre déploiement où Lync Server sera déployé.</p></td>
<td><p>Dans le domaine racine de chaque forêt où Lync Server sera déployé. Pour exécuter cette étape, vous devez être membre du groupe administrateurs d’entreprise.</p>
<div>

> [!NOTE]  
> Dans une topologie de forêt de ressources, exécutez cette étape uniquement dans la forêt de ressources, et non dans les forêts utilisateurs. Dans une topologie de forêt centrale, exécutez cette étape uniquement dans la forêt centrale et non dans les forêts utilisateurs.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Préparation des domaines pour Lync Server 2013</a></p></td>
<td><p>Ajoute des autorisations sur les objets à utiliser par les membres de groupes universels.</p>
<p>S’exécute une fois par domaine d’utilisateur ou domaine de serveur.</p>
<div>

> [!NOTE]  
> Si vous effectuez une migration de Lync Server 2010 vers Lync Server 2013, l’Assistant déploiement peut indiquer que la préparation du domaine est déjà terminée. Vous n’avez pas besoin de réexécuter la préparation du domaine. Les autorisations n’ont pas été modifiées de Lync Server 2010 vers Lync Server 2013.


</div></td>
<td><p>Sur un serveur membre de chaque domaine sur lequel Lync Server sera déployé. Pour exécuter cette étape, vous devez être membre du groupe Domain Admins.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013, comme Lync Server 2010, stocke une grande partie des informations de configuration dans le magasin central de gestion plutôt que dans AD DS, comme dans le cas d’Office Communications Server 2007 R2. Toutefois, les informations suivantes sont stockées dans AD DS:

  - **Extensions de schéma**:
    
      - Extensions de l’objet utilisateur
    
      - Extensions pour les classes Office Communications Server 2007 R2 permettant de garantir la compatibilité descendante

<!-- end list -->

  - **Data (données** ) (stockés dans le schéma étendu de Lync Server et dans les classes de schéma existantes):
    
      - URL (Uniform Resource Identifier) de l’utilisateur SIP et autres paramètres utilisateur
    
      - Objets de contact pour des applications telles que Response Group et attendant
    
      - Pointeur vers le magasin de gestion central
    
      - Compte d’authentification Kerberos (objet facultatif de l’ordinateur)

Dans Lync Server 2013, vous déléguez le programme d’installation et d’administration en accordant des autorisations de configuration au groupe universel RTCUniversalServerAdmins de sorte que les membres de ce groupe puissent installer et activer Lync Server 2013 sur un serveur local (après avoir ajouté le serveur à topologie, publiée et activée). Les utilisateurs délégués doivent être administrateurs locaux sur l’ordinateur sur lequel ils installent et activent Lync Server 2013, mais ils n’ont pas besoin d’être membres du groupe administrateurs de domaine. Vous pouvez également accorder des autorisations pour les objets dans des unités d’organisation (UO) spécifiques de sorte que les membres des groupes universels créés lors de la préparation de la forêt puissent accéder à ces objets sans être membres du groupe administrateurs de domaine.

Pour les nouveaux déploiements de Lync Server 2013, les paramètres globaux doivent être stockés dans le conteneur de configuration. Si votre organisation effectue une mise à niveau à partir d’une version antérieure et que vous avez encore des paramètres globaux dans le conteneur système, le conteneur système est toujours pris en charge.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Attributs, classes et extensions des schémas Active Directory utilisés par Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

