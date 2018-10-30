---
title: Vérification du bon déroulement de la réplication utilisateur
TOCTitle: Vérification du bon déroulement de la réplication utilisateur
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204712(v=OCS.15)
ms:contentKeyID: 49296400
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification du bon déroulement de la réplication utilisateur

 

_**Dernière rubrique modifiée :** 2012-09-28_

Lors de l’exécution de l’applet de commande **Move-CsLegacyUser** , une défaillance peut se produire en raison de l’absence de synchronisation des informations utilisateur entre les services de domaine Active Directory et les bases de données Lync Server 2013, due à l’inachèvement de la réplication initiale. Le temps nécessaire à l’exécution de la synchronisation initiale du service du réplicateur d’utilisateurs de Lync Server 2013 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le pool Lync Server 2013. Le processus de synchronisation initiale du service du réplicateur d’utilisateurs de Lync Server 2013 a lieu lorsque Lync Server 2013 démarre pour la première fois. Par la suite, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs. Effectuez les étapes suivantes pour vérifier si la réplication utilisateur s’est déroulée correctement avant d’exécuter l’applet de commande **Move-CsLegacyUser** .

## Pour vérifier que la réplication utilisateur est terminée

1.  Dans le serveur frontal Lync Server 2013, cliquez sur le menu **Démarrer** , puis sur **Exécuter** .

2.  Entrez **eventvwr.exe** , puis cliquez sur **OK** .

3.  Dans l’Observateur d’événements, cliquez sur **Journaux des applications et des services** pour développer l’élément, puis sélectionnez Lync Server.

4.  Dans le volet **Actions** , cliquez sur **Filtrer le journal actuel** .

5.  Dans la liste **Sources d’événements** , cliquez sur **LS User Replicator** .

6.  Dans **\<Tous les ID d’événements\>** , entrez **30024** , puis cliquez sur **OK** .

7.  Dans la liste d’événements filtrés, sous l’onglet **Général** , recherchez une entrée qui indique que la réplication utilisateur s’est terminée avec succès.

