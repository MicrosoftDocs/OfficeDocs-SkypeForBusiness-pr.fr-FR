---
title: Configuration d’AD FS 2.0 pour prendre en charge l’authentification du client
TOCTitle: Configuration d’AD FS 2.0 pour prendre en charge l’authentification du client
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn308565(v=OCS.15)
ms:contentKeyID: 56269579
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’AD FS 2.0 pour prendre en charge l’authentification du client

 

_**Dernière rubrique modifiée :** 2016-12-08_

Deux types d’authentifications peuvent être configurés pour permettre à AD FS 2.0 de prendre en charge l’authentification à l’aide de cartes à puce :

  - authentification basée sur les formulaires ;

  - authentification de client TLS (Transport Layer Security).

L’authentification basée sur les formulaires vous permet de développer une page web via laquelle les utilisateurs s’authentifient à l’aide de leurs nom d’utilisateur et mot de passe, ou de leurs carte à puce et code confidentiel. Cette rubrique décrit l’implémentation de l’authentification de client TLS (Transport Layer Security) avec AD FS 2.0. Pour plus d’informations sur les types d’authentifications AD FS 2.0, voir la rubrique « AD FS 2.0 : modification du type d’authentification local » à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).


**Pour configurer AD FS 2.0 pour prendre en charge l’authentification du client**

1.  Connectez-vous à l’ordinateur AD FS 2.0 à l’aide d’un compte d’administrateur de domaine.

2.  Lancez l’Explorateur Windows.

3.  Accédez à C:\\inetpub\\adfs\\ls.

4.  Effectuez une copie de sauvegarde du fichier web.config existant.

5.  Ouvrez le fichier web.config existant à l’aide du Bloc-notes.

6.  Dans la barre de menus, sélectionnez **Edition**, puis **Rechercher**.

7.  Recherchez **\<localAuthenticationTypes\>**.
    
    Quatre types d’authentifications apparaissent (un par ligne).

8.  Déplacez la ligne contenant le type d’authentification TLSClient au début de la liste dans la section.

9.  Enregistrez et fermez le fichier web.config.

10. Démarrez une invite de commandes avec des privilèges élevés.

11. Redémarrez IIS en exécutant la commande suivante :
    
        IISReset /Restart /NoForce

