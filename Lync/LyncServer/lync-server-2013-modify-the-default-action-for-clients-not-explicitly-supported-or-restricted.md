---
title: "Mod. l’action par déf. des clients non explicitement pris en ch. ou restreints"
TOCtitle: "Mod. l’action par déf. des clients non explicitement pris en ch. ou restreints"
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520994(v=OCS.15)
ms:contentKeyID: 49297269
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modifier l’action par défaut des clients qui ne sont pas explicitement pris en charge ou restreints

 

_**Dernière rubrique modifiée :** 2013-02-23_

En plus de spécifier la version des clients que vous souhaitez prendre en charge dans votre environnement Lync Server 2013, vous pouvez également affecter une action par défaut aux clients pour lesquels aucune stratégie de version n’a encore été définie. Cela vous permet de restreindre les versions des clients utilisées dans votre environnement Lync Server, ce qui peut vous aider à contrôler les coûts associés à la prise en charge de plusieurs versions de clients.

## Pour modifier l’action par défaut des clients qui ne sont pas explicitement pris en charge ou restreints

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration de la version du client**.

4.  Dans la page **Configuration de la version du client**, double-cliquez sur la configuration **Global** dans la liste.

5.  Dans la boîte de dialogue **Modifier la configuration de la version du client**, vérifiez que la case à cocher **Activer le contrôle de version** est activée puis, sous **Action par défaut**, sélectionnez l’une des options suivantes :
    
      - **Autoriser**   Autorise le client à se connecter si sa version ne correspond à aucun filtre de la liste **Stratégies de version du client**.
    
      - **Bloquer**   Empêche le client de se connecter si sa version ne correspond à aucun filtre de la liste **Stratégies de version du client**.
    
      - **Bloquer avec une URL**   Empêche le client de se connecter si sa version ne correspond à aucun filtre de la liste **Stratégies de version du client** et affiche un message d’erreur contenant une URL à partir de laquelle un client plus récent peut être téléchargé.
    
      - **Autoriser avec une URL**   Autorise le client à se connecter si sa version ne correspond à aucun filtre de la liste **Stratégies de version du client** et affiche un message d’erreur contenant une URL à partir de laquelle un client plus récent peut être téléchargé.

6.  Si vous avez sélectionné **Bloquer avec une URL**, dans la zone **URL**, tapez l’URL de téléchargement du client à inclure dans le message d’erreur.

7.  Cliquez sur **Valider**.

## Pour désactiver le contrôle de version des clients

  - Pour désactiver le contrôle de version afin d’autoriser tous les clients à se connecter quelle que soit leur version, désactivez la case à cocher **Activer le contrôle de version**, puis cliquez sur **Valider**.

## Modification de l’action par défaut à l’aide des applets de commande Lync Server PowerShell

L’action par défaut à exécuter quand des utilisateurs tentent de se connecter à l’aide de clients qui ne sont pas explicitement pris en charge ou limités par une stratégie de version des clients peut également être gérée via l’interface de ligne de commande Windows PowerShell et l’applet de commande **Set-CsClientVersionPolicy**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Configuration de l’action par défaut pour bloquer l’accès

  - La commande suivante définit l’action par défaut du site Redmond à Block. Elle permet de bloquer l’inscription des clients pour lesquels il n’existe aucune règle de configuration des versions des clients.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

## Configuration de l’action par défaut pour autoriser l’accès

  - Dans cet exemple, l’action par défaut du site Redmond est définie à Allow. Cela permet d’autoriser l’inscription des clients pour lesquels il n’existe aucune règle de configuration des versions des clients.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionPolicy).

## Voir aussi

#### Autres ressources

[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

