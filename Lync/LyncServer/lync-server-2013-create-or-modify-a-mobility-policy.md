---
title: Création ou modification d’une stratégie de mobilité
TOCTitle: Création ou modification d’une stratégie de mobilité
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49891625
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une stratégie de mobilité

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez créer ou modifier une stratégie de mobilité pour permettre aux utilisateurs mobiles d’utiliser les périphériques mobiles pris en charge pour les fonctionnalités Lync, comme la messagerie instantanée, la présence et les contacts. Vous pouvez créer ou modifier les stratégies de mobilité depuis le Panneau de configuration Lync Server 2013 ou l’environnement de ligne de commande Lync Server 2013 Management Shell.

## Pour créer une stratégie de mobilité depuis le Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Stratégie de mobilité**.

4.  Sur la page **Stratégie de mobilité**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
    1.  Pour créer une stratégie de mobilité de site, cliquez sur **Stratégie de site**, cliquez sur un site, cliquez sur **OK**, vérifiez les paramètres par défaut, puis, le cas échéant, effectuez les modifications nécessaires.
    
    2.  Pour créer une stratégie de mobilité utilisateur, cliquez sur **Stratégie de l’utilisateur**, tapez un nom, vérifiez les paramètres par défaut, puis, le cas échéant, effectuez les modifications nécessaires.

5.  Cliquez sur **Valider**.

## Pour modifier une stratégie de mobilité depuis le Panneau de configuration Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Stratégie de mobilité**.

4.  Sur la page **Stratégie de mobilité**, cliquez sur l’une des stratégies de mobilité existantes.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Modifiez les paramètres de votre choix.

7.  Cliquez sur **Valider**.

## Suppression des stratégies d’accès externe en utilisant les cmdlets Windows PowerShell

Vous pouvez également créer des stratégies de mobilité (sur une étendue de site ou une étendue par utilisateur) en utilisant Windows PowerShell et la cmdlet **New-CsMobilityPolicy**. De plus, vous pouvez utiliser la cmdlet **Set-CsMobilityPolicy** pour modifier l’une de vos stratégies existantes, notamment la stratégie globale. Ces cmdlets peuvent être exécutées depuis l’environnement de ligne de commande Lync Server 2013 Management Shell ou depuis une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Création d’une stratégie de mobilité sur l’étendue Site

  - Cette commande crée une stratégie de mobilité pour le site Redmond :
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Étant donné qu’aucun paramètre n’est spécifié dans la commande précédente (sauf le paramètre obligatoire Identity), les stratégies utiliseront les valeurs par défaut pour toutes ses propriétés.

## Création d’une stratégie de mobilité sur l’étendue Utilisateur

  - Pour créer une stratégie de mobilité sur l’étendue Utilisateur, spécifiez un paramètre Identity unique pour la stratégie :
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

## Modification d’une seule valeur de propriété durant la création d’une stratégie de mobilité

  - Pour créer des stratégies utilisant différentes valeurs de propriétés, incluez le paramètre et la valeur de paramètre appropriés. Par exemple, cette commande crée une stratégie de mobilité désactivant la fonctionnalité Appel via le bureau :
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

## Modification de plusieurs valeurs de propriété durant la création d’une stratégie de mobilité

  - Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres. Par exemple, cette commande crée une stratégie désactivant à la fois la mobilité et la fonctionnalité Appel via le bureau :
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

Pour plus d’informations, recherchez les cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy) et [Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy) dans la rubrique d’aide.

## Voir aussi

#### Tâches

[Configuration de la stratégie de mobilité dans Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

