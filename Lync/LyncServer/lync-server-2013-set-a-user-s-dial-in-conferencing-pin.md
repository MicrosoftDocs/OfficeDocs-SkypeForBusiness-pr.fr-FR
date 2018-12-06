---
title: "Lync Server 2013 : Déf. du code conf. de conférence rdv d’un utilisateur"
TOCTitle: Définition du code confidentiel de conférence rendez-vous d’un utilisateur
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520985(v=OCS.15)
ms:contentKeyID: 49297033
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition du code confidentiel de conférence rendez-vous d’un utilisateur dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-06-10_

Pour participer à une conférence rendez-vous en tant qu’utilisateur authentifié, un utilisateur Lync Server 2013 ayant des informations d’identification de services de domaine Active Directory (AD DS) requiert un code confidentiel (PIN). Si un utilisateur a oublié le code confidentiel de la conférence rendez-vous ou qu’il ne l’a pas défini via Lync Server, vous pouvez définir celui-ci à partir du Panneau de configuration Lync Server. Vous pouvez générer automatiquement le code confidentiel ou en créer un manuellement.

> [!NOTE]  
> Les caractéristiques spécifiques du code confidentiel, comme sa longueur minimale, peuvent être définies en tant que stratégie. En plus de la stratégie globale, vous pouvez configurer une stratégie de code confidentiel pour un site ou un utilisateur particulier. Pour plus d’informations sur la configuration d’une stratégie de code confidentiel, reportez-vous à <a href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configurer les règles de code confidentiel des conférences rendez-vous dans Lync Server 2013</a>.

## Pour définir le code confidentiel d’un utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à** ).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        
        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <strong>Ajouter un filtre</strong>.    
    5.  Cliquez sur **Rechercher**.
    
    > [!NOTE]  
    > Si le code confidentiel est verrouillé, vous devez le déverrouiller avant de pouvoir le définir. Pour déverrouiller le code confidentiel, cliquez sur l’utilisateur, sur <strong>Action</strong>, puis sur <strong>Déverrouiller le code confidentiel</strong>.

6.  Cliquez sur un utilisateur dans les résultats de recherche, puis cliquez sur **Action** et sur **Définir le code confidentiel**.

7.  Dans la boîte de dialogue **Définir le code confidentiel**, effectuez l’une des opérations suivantes :
    
      - Pour autoriser Lync Server 2013 à générer le code confidentiel de l’utilisateur, sélectionnez **Générer automatiquement un code confidentiel valide** (valeur par défaut).
    
      - Pour créer votre propre code confidentiel, cliquez sur **Entrer manuellement un code confidentiel spécifique**, cliquez sur la zone de texte, puis tapez un code confidentiel respectant les exigences de code confidentiel spécifiées dans vos paramètres de stratégie de code confidentiel.

8.  Cliquez sur **OK**.

9.  Dans **Définir le code confidentiel**, effectuez l’une des opérations suivantes :
    
      - Activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le et communiquez-le à l’utilisateur selon la méthode préférée de votre organisation.
    
      - Cliquez sur **Ouvrir mon application de messagerie pour envoyer le nouveau code confidentiel à l’utilisateur** afin d’envoyer le code confidentiel par courrier électronique. Si Microsoft Office Outlook est votre client de messagerie, le code confidentiel est automatiquement copié dans un nouveau message électronique. Si vous utilisez un autre client de messagerie, activez la case à cocher **Afficher le code confidentiel** pour afficher le code confidentiel, puis copiez-le dans votre message électronique.

10. Cliquez sur **Fermer**.

## Affecter un code confidentiel à un utilisateur via les applets de commande Windows PowerShell

Vous pouvez également affecter plusieurs codes confidentiels à l’aide de l’applet de commande Set-CsClientPin. Vous pouvez l’exécuter depuis le Lync Server 2013 Management Shell ou une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affecter automatiquement un code confidentiel à un utilisateur

  - La commande suivante affecte un code confidentiel à l’utilisateur Ken Myer. Comme le paramètre de code confidentiel n’est pas inclus, Lync Server génère et affecte automatiquement le code confidentiel.
    
        Set-CsClientPin -Identity "Ken Myer" 

## Affecter un code PIN à un utilisateur

  - Cette commande utilise le paramètre de code confidentiel pour affecter le code confidentiel 121989 à l’utilisateur Ken Myer.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

Pour plus d’informations, reportez-vous à la rubrique d’aide sur l’applet de commande [Set-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPin).

## Voir aussi

#### Concepts

[Numéro d’accès entrant](https://technet.microsoft.com/fr-fr/library/gg133674\(v=ocs.15\))  

#### Autres ressources

[Configurer les règles de code confidentiel des conférences rendez-vous dans Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)

