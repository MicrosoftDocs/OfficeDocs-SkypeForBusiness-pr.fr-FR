---
title: "LS 2013 : Vue d’ens. de la prép. des services de domaine Active Directory"
TOCTitle: Vue d’ensemble de la préparation des services de domaine Active Directory
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398869(v=OCS.15)
ms:contentKeyID: 49298862
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de la préparation des services de domaine Active Directory dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour préparer services de domaine Active Directory au déploiement Lync Server 2013, vous devez exécutez trois étapes en respectant un ordre spécifique.

Le tableau ci-dessous décrit les étapes à suivre en vue de préparer AD DS pour Lync Server.

### Étapes de préparation d’Active Directory

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
<th>Emplacement d’exécution</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Préparation du schéma Active Directory dans Lync Server 2013</a></p></td>
<td><p>Étend le schéma Active Directory en ajoutant de nouvelles classes et de nouveaux attributs utilisés par Lync Server.</p>
<p>Exécutez cette opération une seule fois pour chaque forêt dans votre déploiement où Lync Server sera déployé.</p></td>
<td><p>Sur le contrôleur de schéma, dans le domaine racine de chaque forêt dans laquelle Lync Server sera déployé.</p>

> [!NOTE]  
> Il n’est pas nécessaire d’exécuter cette étape dans le domaine racine si vous disposez d’autorisations sur le contrôleur de schéma, mais vous devez être membre du groupe Administrateurs du schéma dans le domaine racine et membre du groupe Administrateurs d’entreprise sur le contrôleur de schéma. Dans une topologie de forêt de ressources, exécutez cette étape uniquement dans la forêt de ressources, et non dans les forêts d’utilisateurs. Dans une topologie de forêt centrale, exécutez cette étape uniquement dans la forêt centrale, et non dans les forêts d’utilisateurs.

</td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Préparation de la forêt pour Lync Server 2013</a></p></td>
<td><p>Crée des paramètres globaux et des groupes universels utilisés par Lync Server.</p>
<p>Exécutez cette opération une seule fois pour chaque forêt dans votre déploiement où Lync Server sera déployé.</p></td>
<td><p>Dans le domaine racine de chaque forêt dans laquelle Lync Server sera déployé. Pour effectuer cette tâche, vous devez être membre du groupe Administrateurs d’entreprise.</p>

> [!NOTE]  
> Dans une topologie de forêt de ressources, exécutez cette étape uniquement dans la forêt de ressources, et non dans les forêts d’utilisateurs. Dans une topologie de forêt centrale, exécutez cette étape uniquement dans la forêt centrale, et non dans les forêts d’utilisateurs.

</td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Préparation des domaines pour Lync Server 2013</a></p></td>
<td><p>Ajoute des autorisations sur les objets utilisés par les membres de groupes universels.</p>
<p>Exécutez cette opération une seule fois par domaine utilisateur ou domaine serveur.</p>

> [!NOTE]  
> Si vous migrez de Lync Server 2013 vers Lync Server 2010, l’Assistant Déploiement peut indiquer que la préparation du domaine est déjà terminée. Vous n’avez pas besoin de relancer la préparation du domaine. Les autorisations n’ont subi aucune modification entre Lync Server 2013 et Lync Server 2010.

</td>
<td><p>Sur un serveur membre dans chaque domaine où Lync Server sera déployé. Pour effectuer cette tâche, vous devez être membre du groupe Administrateurs du domaine.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013, comme Lync Server 2010, enregistre la plupart des informations de configuration dans le magasin central de gestion, et non plus dans AD DS comme dans Office Communications Server 2007 R2. Cependant, les informations suivantes sont enregistrées dans AD DS :

  - **Extensions de schéma** :
    
      - Extensions de l’objet utilisateur
    
      - Extensions pour les classes Office Communications Server 2007 R2 pour maintenir la compatibilité descendante

<!-- end list -->

  - **Données** (enregistrées dans le schéma étendu Lync Server et dans les classes de schéma existantes) :
    
      - URI (Uniform Resource Identifier) SIP de l’utilisateur et autres paramètres utilisateur
    
      - Objets contact pour des applications telles que le service Response Group et l’Intendant Conférence
    
      - Un pointeur vers le magasin central de gestion
    
      - Compte d’authentification Kerberos (un objet ordinateur facultatif)

Dans Lync Server 2013, vous déléguez l’installation et l’administration en accordant des autorisations d’installation au groupe universel RTCUniversalServerAdmins afin que les membres de ce groupe puissent installer et activer Lync Server 2013 sur un serveur local (une fois que le serveur a été ajouté à la topologie publiée et activée). Les utilisateurs délégués doivent être des administrateurs locaux sur l’ordinateur où ils installent et activent Lync Server 2013, mais ils n’ont pas besoin d’être membres du groupe Administrateurs du domaine. Vous pouvez également accorder des autorisations pour des objets dans des unités d’organisation spécifiées afin que les membres des groupes universels créés lors de la préparation de la forêt puissent accéder à ces objets sans être membres du groupe Administrateurs du domaine.

Pour les nouveaux déploiements de Lync Server 2013, les paramètres globaux doivent être stockés dans le conteneur de configuration. Si votre entreprise procède à une mise à niveau d’une version antérieure et que des paramètres globaux figurent toujours dans le conteneur système, celui-ci est toujours pris en charge.

## Voir aussi

#### Concepts

[Préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Attributs, classes et extensions des schémas Active Directory utilisés par Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  

#### Autres ressources

[Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Préparation des domaines pour Lync Server 2013](lync-server-2013-preparing-domains.md)

