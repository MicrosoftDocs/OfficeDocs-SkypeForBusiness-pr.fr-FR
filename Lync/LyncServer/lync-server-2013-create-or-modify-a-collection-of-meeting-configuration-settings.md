---
title: "Créa. ou modif. d’une coll. de param. de conf. de réunion ds Lync Server 2013"
TOCtitle: "Créa. ou modif. d’une coll. de param. de conf. de réunion ds Lync Server 2013"
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49891549
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une collection de paramètres de configuration de réunion dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les paramètres de la page Configuration de la réunion permettent de définir diverses caractéristiques de l’expérience de participation aux réunions. Par défaut, les paramètres globaux définissent la participation aux réunions. Vous pouvez également créer des paramètres de participation aux réunions au niveau du site et du pool. Si vous créez des paramètres au niveau du pool, ceux-ci s’appliquent à toutes les réunions hébergées par ce pool. Si vous ne créez pas de paramètres au niveau du pool, les paramètres au niveau du site s’appliquent s’ils existent. Si vous ne définissez pas de paramètres au niveau du site, les paramètres globaux s’appliquent à toutes les réunions.

## Pour créer des paramètres de participation aux réunions

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.

4.  Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.
    
      - Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.

5.  Pour acheminer les participants qui appellent depuis le réseau téléphonique commuté (RTC) via la salle d’attente, désactivez la case à cocher **Les appelants PSTN ignorent la salle d’attente**. Par défaut, les participants qui appellent depuis un réseau RTC accèdent directement à la réunion.

6.  Pour désigner le présentateur de la réunion, dans **Désigné comme présentateur**, effectuez l’une des opérations suivantes :
    
      - Pour n’autoriser que l’organisateur à être présentateur, cliquez sur **Aucun**.
    
      - Pour n’autoriser que les participants membres de votre entreprise à être présentateur, cliquez sur **Société**. Il s’agit du paramètre par défaut.
    
      - Pour autoriser tous les participants à être présentateur, cliquez sur **Tout le monde**.

7.  Pour permettre à l’organisateur de sélectionner un type de conférence lors de la planification d’une réunion, désactivez la case à cocher **Type de conférence affecté par défaut**. Par défaut, le type de conférence est automatiquement affecté.

8.  Pour empêcher les utilisateurs anonymes (non identifiés) d’être automatiquement admis, désactivez la case à cocher **Admettre les utilisateurs anonymes par défaut**. Par défaut, les utilisateurs anonymes sont automatiquement admis aux réunions.

9.  Pour personnaliser l’invitation à la réunion envoyée aux participants, procédez comme suit. Notez que la longueur maximale des URL et du texte de pied de page personnalisé est de 1 Ko. Sauf pour l’**URL de l’aide**, si vous ne spécifiez pas une valeur pour les personnalisations, elles ne seront pas incluses dans la réunion. Si vous n’incluez pas d’URL de l’aide personnalisée, l’URL de l’aide par défaut pour Lync est affichée dans l’invitation.
    
      - Pour personnaliser le logo qui apparaît dans l’invitation à la réunion, dans **URL du logo**, entrez l’emplacement du logo.
        
        > [!NOTE]  
        > Le logo doit être une image GIF ou JPG d’une taille de 188 par 30 pixels.    
      - Pour personnaliser le texte d’aide qui apparaît dans l’invitation à la réunion, dans **URL de l’aide**, entrez l’emplacement du texte d’aide.
    
      - Pour personnaliser les informations légales qui apparaissent dans l’invitation à la réunion, dans **URL des informations légales**, entrez l’emplacement des informations légales.
    
      - Pour personnaliser le texte de pied de page qui apparaît dans l’invitation à la réunion, dans **Texte de pied de page personnalisé**, entrez le texte.

10. Cliquez sur **Valider**.

## Pour modifier une collection existante de configurations de réunion

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **Conférence**, puis cliquez sur **Configuration de la réunion**.

4.  Dans la liste des configurations de réunion, cliquez sur la configuration à modifier, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration de la réunion**, modifiez les paramètres de configuration, à l’exception du nom de configuration qui ne peut pas être modifié.

6.  Cliquez sur **Valider**.

## Création de paramètres de configuration de réunion à l’aide d’applets de commande Windows PowerShell

Les paramètres de configuration de réunion peuvent également être créés (au niveau de l’étendue du site) à l’aide de Windows PowerShell et de l’applet de commande New-CsMeetingConfiguration. Cette dernière peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour créer des paramètres de configuration de réunion qui utilisent les valeurs par défaut

  - Cette commande crée un ensemble de paramètres de configuration de réunion pour le site de Redmond :
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    Comme aucun paramètre (autre que le paramètre d’identité obligatoire) n’est spécifié dans la commande précédente, les nouveaux paramètres de configuration de réunion utiliseront les valeurs par défaut pour toutes ses propriétés.

## Pour modifier une valeur de propriété lors de la création de paramètres de configuration de réunion

  - Pour créer des paramètres qui utilisent différentes valeurs de propriété, incluez simplement le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de réunion qui, par défaut, admet tout le monde à une réunion comme présentateur, utilisez une commande semblable à la suivante :
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

## Pour modifier plusieurs valeurs de propriétés lors de la création de paramètres de configuration de réunion

  - Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres. Par exemple, cette commande admet tout le monde à une réunion comme présentateur et force aussi les utilisateurs PSTN à attendre dans la salle d’attente jusqu’à ce qu’ils soient officiellement admis à la réunion :
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

Pour plus d’informations, voir la rubrique d’aide associée à l’applet de commande [New-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMeetingConfiguration).

