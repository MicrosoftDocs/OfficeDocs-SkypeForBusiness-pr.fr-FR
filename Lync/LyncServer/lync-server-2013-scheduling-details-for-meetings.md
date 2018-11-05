---
title: Détails de planification
TOCTitle: Détails de planification
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204823(v=OCS.15)
ms:contentKeyID: 49296918
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Détails de planification

 

_**Dernière rubrique modifiée :** 2012-10-04_

Après s’être assurée qu’aucune autre réunion n’est prévue à l’heure demandée, l’équipe de support des grandes réunions qui traite la demande planifie la réunion dans le pool de grandes réunions. Servez-vous du complément de réunion en ligne pour Lync qui est installé avec le client Lync Server 2013 pour effectuer cette tâche, en utilisant les informations d’identification d’un utilisateur habilité à utiliser Lync Server dans le pool de grandes réunions dédié.

Pour assurer la meilleure expérience utilisateur possible, il est important de planifier les grandes réunions avec les niveaux d’accès et les paramètres de réunion appropriés, en fonction des besoins de l’organisateur de la réunion. Nous vous recommandons de configurer les options de réunion Lync en utilisant les paramètres de planification suivants :

  - Utilisez un nouvel espace de réunion pour chaque grande réunion au lieu de réutiliser l’espace de réunion dédié.

  - Spécifiez le niveau d’accès à la réunion comme suit :
    
      - Si au moins un invité ne fait pas partie de l’organisation, optez pour le type d’accès à la réunion **Tout le monde (aucune restriction)**. Cela vous évitera ainsi d’avoir à gérer une grande salle d’attente pendant le déroulement de la réunion.
    
      - S’il s’agit d’une réunion interne, optez pour le type d’accès à la réunion **Toute personne de ma société**.
        
        > [!NOTE]  
        > Évitez de choisir le type d’accès à la réunion <strong>Personnes de ma société invitées</strong>. En effet, ce paramètre contraint les organisateurs à ajouter toutes les adresses de messagerie des utilisateurs à la liste d’invités et il vous empêche d’inviter un groupe de distribution.<br />
        Évitez de choisir le type d’accès à la réunion <strong>Seulement moi, l’organisateur de la réunion</strong>, car ce paramètre exige que chaque participant à la réunion, y compris les présentateurs, se trouve dans la salle d’attente à l’heure d’exécution de la réunion. La personne responsable de l’exécution de la grande réunion doit alors constamment surveiller la liste de la salle d’attente et admettre les nouveaux utilisateurs qui se trouvent dans la salle d’attente.

  - Autorisez les utilisateurs qui se connectent à partir d’un téléphone à accéder automatiquement à la réunion en cochant le paramètre **Les appelants sont admis directement**.

  - Invitez explicitement les utilisateurs suivants :
    
      - organisateur de la réunion et délégué (demandeur) ;
    
      - liste des présentateurs fournie par un demandeur de réunion.
    
    > [!NOTE]  
    > Si le type d’accès à la réunion défini est <strong>Personnes que je choisis</strong>, vous devez ajouter explicitement chaque participant à une grande réunion en tant qu’invité de la réunion.

  - Au lieu d’attribuer à l’option de présentateur l’une des valeurs de promotion automatique, gérez explicitement les présentateurs. Veillez à ajouter les utilisateurs suivants en tant que présentateurs :
    
      - organisateur de la réunion et délégué (demandeur) ;
    
      - liste des présentateurs fournie par les demandeurs de grande réunion.
    
    > [!NOTE]  
    > En gérant explicitement les présentateurs, vous pouvez contrôler le nombre de présentateurs et ainsi favoriser le bon déroulement d’une grande réunion, avec un nombre de présentateurs limité. Si la majorité des participants à la réunion ont un rôle de participant, cela limite les chances de voir des personnes prendre accidentellement le contrôle de la présentation, supprimer une présentation PowerPoint, désactiver ou activer le son pour les présentateurs et perturber le déroulement de la réunion.

  - Cochez le paramètre **Désactiver le son pour tous les participants** pour faire en sorte que seuls les présentateurs puissent diffuser du son au cours de la réunion.

  - Cochez le paramètre **Bloquer la vidéo des participants** pour faire en sorte que seuls les présentateurs puissent diffuser des vidéos au cours de la réunion.

La figure suivante présente les paramètres recommandés pour le complément de réunion en ligne pour Lync.

![Options de réunion conférence](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "Options de réunion conférence")

