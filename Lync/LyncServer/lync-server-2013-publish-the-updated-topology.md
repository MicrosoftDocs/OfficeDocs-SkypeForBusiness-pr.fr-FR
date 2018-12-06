---
title: 'Lync Server 2013 : Publication de la topologie mise à jour'
TOCTitle: Publication de la topologie mise à jour
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204910(v=OCS.15)
ms:contentKeyID: 49297316
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publication de la topologie mise à jour dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-01_

Après avoir mis à jour votre topologie dans le Générateur de topologie, vous devez la publier dans le magasin central de gestion pour pouvoir configurer et utiliser le serveur de conversations permanentes. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.

## Pour publier une topologie mise à jour

Avant de publier votre topologie, installez les bases de données du serveur de conversations permanentes. Utilisez le Générateur de topologie pour installer les bases de données en sélectionnant **Action** et **Installer une base de données** .

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, connectez-vous à l’aide d’un compte membre à la fois du groupe **Admins du domaine** et du groupe **RTCUniversalServerAdmins** et qui dispose des autorisations de contrôle total (c’est-à-dire, lecture, écriture et modification) sur le magasin de fichiers à utiliser en tant que magasin de fichiers du serveur de conversations permanentes (afin que le Générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaire (DACL) nécessaires), ou à l’aide d’un compte muni de droits d’utilisateur équivalents.

2.  Démarrez le Générateur de topologie. Sélectionnez **Télécharger la topologie à partir du déploiement existant** ou **Ouvrir une topologie depuis un fichier local** si vous l’avez enregistrée localement.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **Publier la topologie** .

4.  Dans la page **Publier la topologie** , cliquez sur **Suivant** .

5.  Dans la page **Assistant Publication terminé** , assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer** .
    
    > [!IMPORTANT]  
    > Une fois la topologie publiée, vous devez configurer la prise en charge du serveur de conversations permanentes pour permettre l’archivage du contenu.
