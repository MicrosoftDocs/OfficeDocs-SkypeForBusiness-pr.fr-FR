---
title: 'Lync Server 2013 : Configuration des compléments pour les salles'
TOCTitle: Configuration des compléments pour les salles
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204878(v=OCS.15)
ms:contentKeyID: 49297174
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des compléments pour les salles dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Dans le Panneau de configuration Lync Server 2013, vous pouvez utiliser la section **Complément** de la page **conversation permanente** pour associer des URL à des salles de conversation permanente. Ces URL s’affichent sur le client Lync 2013 dans la salle de conversation, dans le volet d’extensibilité de conversation. Un administrateur doit ajouter les compléments à la liste de compléments inscrits et les créateurs/responsables de salles de conversation doivent associer les salles à l’un des compléments inscrits pour que les utilisateurs puissent voir cette mise à niveau dans leur client Lync 2013.

Les compléments servent à étendre l’expérience dans la salle. Un complément ordinaire peut inclure une URL pointant vers une application Silverlight qui effectue une interception quand un code de titre est publié dans une salle de conversation et affiche l’historique du titre dans le volet d’extensibilité. En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément pour inclure un contexte partagé, tel que « Tête de liste » ou « Sujet du jour ».

## Pour configurer des compléments pour des salles de conversation

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le Panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes permettant de démarrer le Panneau de configuration Lync Server, reportez-vous à [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell</a> dans la documentation de déploiement.

3.  Dans la barre de navigation de gauche, cliquez sur **conversation permanente**, puis sur **Complément** .
    
    Pour plusieurs déploiements de pool de serveurs de conversations permanentes, sélectionnez le pool approprié dans la liste déroulante.

4.  Dans la page **Complément** , cliquez sur **Nouveau** .

5.  Dans **Sélectionner un service** , sélectionnez le service correspondant au pool de serveurs de conversations permanentes où vous devez créer le complément. Les compléments ne peuvent pas être déplacés d’un pool à un autre ou partagés parmi différents pools.

6.  Dans **Nouveau complément** , procédez comme suit :
    
      - Dans **Nom** , spécifiez un nom pour le nouveau complément.
    
      - Dans **URL** , spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.

7.  Cliquez sur **Valider** .

## Voir aussi

#### Tâches

[Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md)  

#### Concepts

[Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

