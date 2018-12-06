---
title: "Lync Server 2013 : Activ. ou désactiv. de l’accès des utilisateurs anonymes"
TOCTitle: Activation ou désactivation de l’accès des utilisateurs anonymes
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49299315
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation de l’accès des utilisateurs anonymes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-23_

Les utilisateurs anonymes sont des utilisateurs qui ne disposent pas d’un compte utilisateur dans le services de domaine Active Directory de votre organisation ou dans un domaine fédéré pris en charge, mais qui peuvent être invités à participer à distance à des conférences sur site. En autorisant la participation anonyme dans les réunions, vous permettez aux utilisateurs anonymes (c’est à dire, aux utilisateurs dont l’identité est uniquement vérifiée via une clé de réunion ou de conférence) à rejoindre les réunions. Le fait d’autoriser la participation anonyme requiert son activation pour votre organisation.

Si, ultérieurement, vous souhaitez interdire l’accès utilisateur anonyme de façon temporaire ou définitive, vous pouvez désactiver la participation anonyme pour votre organisation. Utilisez la procédure de cette section pour activer ou désactiver l’accès utilisateur anonyme pour votre organisation.

> [!NOTE]  
> L’activation de l’accès utilisateur anonyme pour votre organisation revient simplement à spécifier que vos serveurs exécutant le service Edge d’accès prennent en charge l’accès utilisateur anonyme. Les utilisateurs anonymes ne peuvent pas participer à une réunion dans votre organisation tant que vous n’avez pas également configuré au moins une stratégie de conférence avant de l’appliquer à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Les seuls utilisateurs pouvant inviter des utilisateurs anonymes aux réunions sont les utilisateurs auxquels vous avez attribué une stratégie de conférence configurée pour prendre en charge les utilisateurs anonymes. Pour plus d’informations sur la configuration des stratégies pour la prise en charge de l’invitation des utilisateurs anonymes, reportez-vous à <a href="lync-server-2013-conferencing-policies.md">Stratégies de conférence dans Lync Server 2013</a>.

## Pour activer ou désactiver l’accès utilisateur anonyme pour votre organisation

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès utilisateur anonyme pour votre organisation, activez la case à cocher **Permettre les communications avec des utilisateurs anonymes**.
    
      - Pour désactiver l’accès utilisateur anonyme pour votre organisation, désactivez la case à cocher **Permettre les communications avec des utilisateurs anonymes**.

6.  Cliquez sur **Valider**.

## Activation ou désactivation de l’accès utilisateur anonyme à l’aide des applets de commande Windows PowerShell

Vous pouvez gérer l’accès utilisateur anonyme à l’aide du Windows PowerShell et de l’applet de commande **Set-CsAccessEdgeConfiguration** (exécutable depuis le Lync Server 2013 Management Shell ou une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).).

## Activer l’accès utilisateur anonyme

  - Pour activer l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## Désactiver l’accès utilisateur anonyme

  - Pour désactiver l’accès utilisateur anonyme, définissez la valeur de la propriété **AllowAnonymousUsers** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

## Voir aussi

#### Concepts

[Référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

