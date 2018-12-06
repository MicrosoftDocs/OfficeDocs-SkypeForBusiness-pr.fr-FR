---
title: Restauration des données de surveillance ou d’archivage
TOCTitle: Restauration des données de surveillance ou d’archivage
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202175(v=OCS.15)
ms:contentKeyID: 53095434
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration des données de surveillance ou d’archivage

 

_**Dernière rubrique modifiée :** 2013-02-18_

Restaurer des données de surveillance et d’archivage n’est pas obligatoire pour remettre Lync Server en état de marche après une défaillance. Toutefois, si les données de surveillance et d’archivage sont essentielles pour votre organisation, il est important de restaurer les données après avoir recréé les bases de données.

L’architecture suivante décrit comment utiliser SQL Server Management Studio pour restaurer les données d’archivage ou de surveillance.

## Pour restaurer les données de surveillance ou d’archivage à partir d’un fichier de sauvegarde

1.  Connectez-vous au serveur que vous restaurez en tant que membre du groupe Administrateurs sur l’ordinateur local ou d’un groupe doté de droits d’utilisateur équivalents.

2.  Ouvrez SQL Server Management Studio : cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft SQL Server 2012** ou **Microsoft SQL Server 2008 R2**, puis sur **SQL Server Management Studio**.

3.  Dans **Se connecter au serveur**, connectez-vous à l’instance SQL Server en fournissant au moins le nom du serveur et les informations d’authentification.

4.  Dans **Explorateur d’objets**, cliquez avec le bouton droit sur **Bases de données**, puis cliquez sur **Restaurer la base de données**.

5.  Sous **Sélectionner une page**, cliquez sur **Général**, puis dans **Vers la base de données** sélectionnez le nom de la base de données comme suit :
    
      - Pour une base de données d’archivage, sélectionnez **LcsLog**.
    
      - Pour une base de données CDR (enregistrement des détails des appels), sélectionnez **LcsCDR**.
    
      - Pour une base de données QoE (qualité de l’expérience), sélectionnez **QoEMetrics**.

6.  Cliquez sur **À partir de l’unité**.

7.  Sous **Sélectionnez les jeux de sauvegarde à restaurer**, cliquez sur le fichier de sauvegarde, puis cliquez sur **Restaurer**.

8.  Sous **Sélectionner une page**, cliquez sur **Options**, vérifiez que le chemin d’accès du fichier de données et que le chemin d’accès du journal sont dans le dossier voulu, puis cliquez sur **OK**.

## Pour vérifier que les listes de contrôle d’accès sont correctes

1.  Développez **Bases de données**, développez la base de données d’archivage ou de surveillance, développez **Sécurité**, puis développez **Utilisateurs**.

2.  Vérifiez que le groupe de domaines RTCComponentUniversalServices existe en tant qu’utilisateur.

3.  Si RTCComponentUniversalServices n’existe pas sous **Utilisateurs**, procédez comme suit :
    
    1.  Cliquez avec le bouton droit sur **Utilisateurs**, puis cliquez sur **Nouvel utilisateur**.
    
    2.  Dans **Nom de connexion**, tapez le nom du groupe manquant, RTCComponentUniversalServices.
    
    3.  Sous **Appartenance au rôle de base de données**, sélectionnez l’autorisation **ServerRole**, puis cliquez sur **OK**.
    
    > [!NOTE]  
    > Vous n’avez pas besoin de redémarrer le service d’archivage ou de surveillance.
