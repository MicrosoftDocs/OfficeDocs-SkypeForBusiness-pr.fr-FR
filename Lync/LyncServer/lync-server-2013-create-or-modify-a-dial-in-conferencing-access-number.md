---
title: "Lync Server 2013 : Créa. ou mod. d’un n° d’accès à une conférence rendez-vous"
TOCTitle: Création ou modification d’un numéro d’accès à une conférence rendez-vous
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398126(v=OCS.15)
ms:contentKeyID: 49296146
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’un numéro d’accès à une conférence rendez-vous dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-17_

Suivez ces étapes si vous souhaitez créer ou modifier un numéro d’accès à une conférence rendez-vous.

> [!IMPORTANT]  
> Avant de créer un numéro d’accès entrant, vous devez définir une région de conférence rendez-vous dans le plan de numérotation qui est associé au nouveau numéro d’accès entrant. Plusieurs plans de numérotation peuvent utiliser la même région.

## Pour créer ou modifier un numéro d’accès entrant

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence** , puis sur **Numéro d’accès entrant** .

4.  Dans la page **Numéro d’accès entrant** , effectuez l’une des opérations suivantes :
    
      - Cliquez sur **Nouveau** pour ouvrir **Nouveau numéro d’accès entrant** .
    
      - Cliquez sur l’un des numéros d’accès entrant dans la liste, cliquez sur **Modifier** , puis sur **Afficher les détails** .
        
        > [!NOTE]  
        > Utiliser le champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès entrant peut ne pas produire les résultats que vous attendez. Par conséquent, triez la liste selon la colonne qui vous intéresse pour identifier le numéro d’accès entrant que vous voulez afficher ou modifier.

5.  Dans **Numéro affiché** , tapez le numéro de téléphone que les utilisateurs du réseau téléphonique commuté (RTC) composent pour rejoindre une conférence.
    
    > [!NOTE]  
    > Ce numéro est affiché dans les invitations aux réunions et dans la page web des paramètres des conférences rendez-vous.

6.  Dans **Nom d’affichage** , tapez la description du numéro d’accès entrant. Il s’agit du nom qui est associé au numéro d’accès entrant dans les résultats des recherches dans Lync.
    
    > [!NOTE]  
    > Ce nom est affiché dans le client lorsqu’un utilisateur appelle le numéro d’accès.

7.  Dans **URI de ligne** , tapez le numéro E.164 du numéro d’accès entrant au format d’URI TEL, avec le symbole + avant le numéro et sans espace. Par exemple, tel :+14255550200.
    
    > [!NOTE]  
    > Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous.

8.  Dans **URI SIP** , procédez comme suit :
    
      - Dans la zone de texte, tapez un URI SIP unique pour ce numéro d’accès à une conférence rendez-vous. Cet URI SIP est affiché à différents endroits, notamment dans les messages de notification d’appel et dans les versions précédentes des clients Communicator.
        
        > [!NOTE]  
        > Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous. Il n’est pas possible de modifier l’URI SIP une fois que le numéro d’accès est créé. Le seul moyen de modifier l’URI SIP est de supprimer et de recréer le numéro d’accès.    
      - Dans la zone de liste déroulante, cliquez sur le domaine de l’application Intendant Conférence qui prend en charge ce numéro d’accès entrant.

9.  Dans **Pool** , cliquez sur le pool qui exécute l’instance d’Intendant Conférence qui prend en charge ce numéro d’accès entrant.
    
    > [!NOTE]  
    > Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’applet de commande <strong>Move-CsApplicationEndpoint</strong> ou supprimer et recréer le numéro d’accès.

10. Dans **Langue principale** , cliquez sur la langue des invites pour ce numéro d’accès entrant.
    
    > [!NOTE]  
    > La langue principale est la langue que l’Intendant Conférence utilise pour répondre aux appels. Les langues prises en charge sont affichées avec chaque numéro de téléphone d’accès dans la page web des paramètres des conférences rendez-vous.

11. (Facultatif) Dans **Langues secondaires (quatre au maximum)** , cliquez sur **Ajouter** , sélectionnez les langues supplémentaires que vous souhaitez prendre en charge pour les personnes qui appellent ce numéro d’accès entrant, puis cliquez sur **OK** .
    
    > [!NOTE]  
    > Vous pouvez sélectionner jusqu’à quatre langues secondaires pour chaque numéro d’accès entrant. Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de la conférence à laquelle ils souhaitent participer.

12. Pour ajouter une région pour le numéro d’accès entrant, sous **Régions associées** , cliquez sur **Ajouter** , cliquez sur les régions associées aux plans de numérotation pour ce numéro d’accès entrant, puis cliquez sur **OK** .

13. Pour supprimer une région du numéro d’accès entrant, sous **Régions associées** , cliquez sur la région que vous souhaitez supprimer, puis cliquez sur **Supprimer** .

14. Cliquez sur **Valider** .

