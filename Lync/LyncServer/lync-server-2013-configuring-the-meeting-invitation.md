---
title: Configuration de l’invitation à une réunion
TOCTitle: Configuration de l’invitation à une réunion
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398638(v=OCS.15)
ms:contentKeyID: 49297864
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de l’invitation à une réunion

 

_**Dernière rubrique modifiée :** 2013-07-16_

Vous pouvez personnaliser des invitations à une réunion envoyées par le complément de réunion en ligne pour Lync 2013 en ajoutant les éléments suivants dans le corps de l’invitation :

  - **Le logo de votre organisation** Ajoutez le logo de votre organisation aux invitations de réunion à l’aide de l’option URL du logo. Si les invitations doivent être envoyées à des personnes externes à votre organisation, l’image doit se trouver sur une URL publique. Les formats d’image pris en charge sont GIF et JPG. Bien que Lync Server 2013 stocke les URL sans restriction de taille, il est conseillé d’utiliser des images avec une taille maximale de 30 pixels de haut sur 188 pixels de large.

  - **Un lien d’aide ou de support personnalisé** Ajoutez une URL pour le site web de l’équipe de support ou d’aide de votre organisation. Si les invitations doivent être envoyées à des personnes externes à votre organisation, l’URL doit être publique. La longueur maximale de l’URL est 1 Ko.

  - **Texte d’exclusion de responsabilité** Ajoutez une URL pour un texte légal ou une exclusion de responsabilité qui sera affiché dans les invitations de réunion. Si les invitations doivent être envoyées à des personnes externes à votre organisation, l’URL doit être publique. La longueur maximale de l’URL est 1 Ko.

  - **Texte de pied de page personnalisé** Ajoutez du texte qui s’affichera sous la forme d’un pied de page personnalisé dans l’invitation. La longueur maximale du texte est de 2 Ko.

Vous pouvez configurer ces options en utilisant le Panneau de configuration Lync Server ou Lync Server Management Shell.


**Pour personnaliser l’invitation à une réunion avec le Panneau de configuration Lync Server**

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.

4.  Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis cliquez sur **OK**.
    
      - Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.

5.  Effectuez l’une des opérations suivantes :
    
      - Dans le champ **URL du logo**, tapez l’URL de l’image du logo de votre organisation.
    
      - Dans le champ **URL de l’aide**, tapez l’URL vers le site de support ou d’aide de votre organisation.
    
      - Dans le champ **Informations légales**, tapez l’URL des informations légales ou de l’exclusion de responsabilité que vous voulez ajouter à vos invitations.
    
      - Dans le champ **Texte de pied de page personnalisé**, tapez le texte du pied de page (maximum 2 Ko).

**Pour personnaliser l’invitation à une réunion avec Lync Server Management Shell**

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande **New-CsMeetingConfiguration** ou **Set-CsMeetingConfiguration** pour créer ou configurer les options d’invitation. Par exemple, exécutez :
    
        New-CsMeetingConfiguration -Identity site:Redmond -EnableInviteCustomization $True -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

