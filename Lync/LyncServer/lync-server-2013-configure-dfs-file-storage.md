---
title: 'Lync Server 2013 : Configuration du stockage des fichiers'
TOCTitle: Configuration du stockage des fichiers
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205150(v=OCS.15)
ms:contentKeyID: 49298465
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration du stockage des fichiers pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 prend en charge l’utilisation de partages de fichiers sur un système de fichiers DFS (Distributed File System). Pour plus d’informations sur les systèmes de fichiers DFS pour Windows Server 2008, reportez-vous au Guide de DFS pas à pas pour Windows Server 2008 à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835). Pour utiliser un système de fichiers DFS avec Lync Server 2013, les conditions suivantes doivent être remplies :

  - les espaces de noms sont basés sur un domaine ;

  - tous les serveurs d’espaces de noms exécutent au minimum de Windows 2008.

Le programme d’installation de Lync Server 2013 requiert que les autorisations sur le dossier partagé accordent un accès complet à l’Administrateur. Lync Server 2013 utilisera ensuite les autorisations de fichiers NTFS pour créer les listes de contrôle d’accès aux dossiers. Les autorisations de partage DFS héritées ne seront pas nécessaires pour restreindre l’accès.

Pour plus d’informations sur les exigences liées aux partages de fichiers, reportez-vous à [Prise en charge du stockage des fichiers dans Lync Server 2013](lync-server-2013-file-storage-support.md) dans la documentation de prise en charge.

La procédure suivante décrit comment configurer correctement les autorisations des dossiers partagés à l’aide de l’Assistant Espace de noms DFS (tel que décrit dans le guide de configuration du système de fichiers DFS).

## Pour configurer des autorisations de dossiers partagés

1.  Cliquez successivement sur **Démarrer** , **Tous les programmes** , **Outils d’administration** et **Gestion du système de fichiers distribués DFS** .

2.  Dans l’arborescence de la console du composant logiciel enfichable Gestion du système de fichiers distribués DFS, cliquez avec le bouton droit sur le serveur d’espaces de noms (par exemple, filesrv1.contoso.com), puis cliquez sur **Modifier les paramètres** .

3.  Sélectionnez **Autorisations du dossier partagé** .

4.  Sélectionnez **Utiliser des autorisations personnalisées** .

5.  Pour le groupe Administrateur, sélectionnez ce qui suit sous **Autoriser**  :
    
      - **Contrôle total**
    
      - **Modification**
    
      - **Lecture**

6.  Cliquez sur **Appliquer** , puis sur **OK** .

