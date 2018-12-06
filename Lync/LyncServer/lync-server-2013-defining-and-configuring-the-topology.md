---
title: 'Lync Server 2013 : Définition et configuration de la topologie'
TOCTitle: Définition et configuration de la topologie
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398339(v=OCS.15)
ms:contentKeyID: 49297210
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition et configuration de la topologie dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-14_

Vous pouvez définir et configurer votre topologie à l’aide du Générateur de topologie. Le Générateur de topologie ne nécessite pas que vous soyez membre du groupe Administrateurs local ou d’un groupe de domaines privilégiés (tel que Administrateurs du domaine). Vous pouvez définir votre topologie en tant qu’utilisateur standard. Lorsque vous démarrez Générateur de topologie pour la première fois et lors des sessions de modification ultérieures, le système vous invite à spécifier l’emplacement où le Générateur de topologie doit charger le document de configuration actuel. Les choix sont les suivants :

  - Télécharger la topologie à partir d’un déploiement existant

  - Ouvrir la topologie à partir d’un fichier local

  - Nouvelle topologie

Si vous avez déjà défini une topologie et le magasin central de gestion, choisissez de télécharger une topologie à partir d’un déploiement existant. Le Générateur de topologie lira la base de données et récupérera la définition actuelle. Si vous disposez d’un magasin central de gestion, choisissez toujours cette option.

Si vous n’avez pas défini un magasin central de gestion et que vous souhaitez modifier une configuration précédemment enregistrée, choisissez d’ouvrir la topologie à partir d’un fichier local. Le fichier que vous ouvrirez sera le fichier de configuration qui a été enregistré dans une session précédente. Vous pouvez utiliser cette option pour modifier la topologie précédemment enregistrée.

> [!WARNING]  
> Si vous disposez déjà d’une topologie publiée, ne chargez aucun fichier de configuration local. Choisissez de télécharger la topologie à partir d’un déploiement existant.

Choisissez de créer une nouvelle topologie si vous souhaitez créer une nouvelle configuration de Générateur de topologie. Une conception précédemment enregistrée n’est pas remplacée sauf si vous choisissez de l’enregistrer à la place du fichier que vous avez créé lors d’une session de conception précédente.

Dans chacune de ces options, le système vous invite à spécifier l’emplacement de stockage du fichier de configuration du Générateur de topologie. L’emplacement du fichier peut être un emplacement local, un emplacement partagé sur un partage de fichiers défini ou un média amovible.

## Dans cette section

  - [Définition et configuration d’une topologie dans le générateur de topologie pour Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Définition et configuration d’un pool frontal ou d’un serveur Standard Edition dans Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Déploiement de pools frontaux couplés pour la récupération d’urgence dans Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Déploiement de la mise en miroir SQL pour la haute disponibilité des serveurs principaux dans Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Modification ou configuration des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Sélection du serveur de gestion centralisée dans Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

