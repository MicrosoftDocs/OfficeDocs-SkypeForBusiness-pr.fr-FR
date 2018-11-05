---
title: 'Lync Server 2013 : Activation des utilisateurs pour Voix Entreprise'
TOCTitle: Activation des utilisateurs pour Voix Entreprise
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413011(v=OCS.15)
ms:contentKeyID: 49299325
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation des utilisateurs pour Voix Entreprise dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Après avoir installé des fichiers pour un ou plusieurs serveurs de médiation, configuré le routage des appels sortants et éventuellement déployé une ou plusieurs fonctions Voix Entreprise avancées, vous pouvez utiliser les procédures suivantes pour permettre à un utilisateur de passer des appels en utilisant Voix Entreprise :

> [!NOTE]  
> Parmi ces procédures, seule la première peut être effectuée en utilisant Panneau de configuration Lync Server. Pour les autres procédures, vous pouvez utiliser uniquement Lync Server Management Shell.

  - Activez le compte d’utilisateur pour Voix Entreprise.

  - (Facultatif) Affectez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.

  - (Facultatif) Affectez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.

## Pour activer un compte d’utilisateur pour Voix Entreprise

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour Voix Entreprise.

6.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7.  Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur **Voix Entreprise**.

8.  Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tel:+14255550200).

9.  Cliquez sur **Valider**.

Pour terminer d’activer un utilisateur pour Voix Entreprise, vérifiez que cet utilisateur a reçu une stratégie de voix et un plan de numérotation, de nature globale (par défaut) ou spécifiques à l’utilisateur.

Par défaut, tous les utilisateurs se voient affecter une stratégie de voix et un plan de numérotation d’ordre global. S’il existe une stratégie de voix ou un plan de numérotation au niveau du site sur lequel un compte d’utilisateur est hébergé, cette stratégie de site s’applique automatiquement à l’utilisateur. Pour appliquer une stratégie de voix ou un plan de numérotation à un utilisateur, vous devez exécuter les applets de commande **Grant-CsVoicePolicy** et **Grant-CsDialPlan**. Pour plus d’informations, reportez-vous à la documentation [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md).

## Affectation d’une stratégie de voix

Les stratégies de voix au niveau global ou au niveau du site sont automatiquement affectées à tous les comptes d’utilisateurs activés pour Voix Entreprise. Vous pouvez également créer des stratégie de voix qui s’appliquent à des utilisateurs ou des groupes spécifiques. Ces stratégies utilisateur doivent être explicitement affectées aux utilisateurs ou aux groupes. Si vous voulez utiliser la stratégie de voix globale ou de site pour tous les utilisateurs activés pour Voix Entreprise, vous pouvez ignorer cette rubrique et passer directement à la section Affectation d’un plan de numérotation dans la suite de cette rubrique.

## Pour affecter une stratégie de voix spécifique à l’utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour affecter une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante dans l’invite :
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Exemple :
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    Dans cet exemple, l’utilisateur dont le nom complet est Bob Kelly a reçu la stratégie de voix portant le nom **VoicePolicyJapan**.

Pour plus d’informations sur l’affectation d’une stratégie de voix spécifique à l’utilisateur ou sur l’exécution de l’applet de commande **Grant-CsVoicePolicy**, reportez-vous à la documentation de [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md).

## Affectation d’un plan de numérotation

Pour terminer la configuration des comptes d’utilisateurs des utilisateurs de Voix Entreprise ou de conférence rendez-vous, il convient de leur affecter un plan de numérotation. Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, s’il en existe un, le plan de numérotation au niveau du site si vous n’affectez pas de manière explicite un plan de numérotation utilisateur existant. Si vous voulez utiliser le plan de numérotation global ou de site pour tous les utilisateurs activés pour Voix Entreprise, vous pouvez ignorer cette section.

## Pour affecter un plan de numérotation

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour affecter un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante dans l’invite :
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Exemple :
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    Dans cet exemple, l’utilisateur dont le nom complet est Bob Kelly s’est vu affecter le plan de numérotation utilisateur intitulé **DialPlanJapan**.

Pour plus d’informations sur l’affectation d’un plan de numérotation utilisateur ou sur l’exécution de l’applet de commande **Grant-CsDialPlan**, reportez-vous à la documentation de [Lync Server Management Shell](lync-server-2013-lync-server-management-shell.md).

## Voir aussi

#### Tâches

[Désactivation d’un utilisateur pour Voix Entreprise](lync-server-2013-disable-a-user-for-enterprise-voice.md)

