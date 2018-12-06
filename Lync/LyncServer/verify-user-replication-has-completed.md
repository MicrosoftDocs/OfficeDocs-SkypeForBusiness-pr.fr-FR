---
title: Vérification du bon déroulement de la réplication de l’utilisateur
TOCTitle: Vérification du bon déroulement de la réplication de l’utilisateur
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204680(v=OCS.15)
ms:contentKeyID: 49296297
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification du bon déroulement de la réplication de l’utilisateur

 

_**Dernière rubrique modifiée :** 2012-09-17_

Lors de l’exécution de l’applet de commande **Move-CsUser** , une défaillance peut se produire en raison de l’absence de synchronisation des informations utilisateur entre les services de domaine Active Directory et les bases de données Lync Server 2013, due à l’inachèvement de la réplication initiale. Le temps nécessaire à l’exécution de la synchronisation initiale du service du réplicateur d’utilisateurs de Lync Server 2013 dépend du nombre de contrôleurs de domaine hébergés dans la forêt Active Directory qui héberge le pool Lync Server 2013. Le processus de synchronisation initiale du service du réplicateur d’utilisateurs de Lync Server 2013 a lieu lorsque Lync Server 2013 démarre pour la première fois. Par la suite, la synchronisation est basée sur l’intervalle du réplicateur d’utilisateurs. Effectuez les étapes suivantes pour vérifier que la réplication utilisateur s’est déroulée correctement avant d’exécuter l’applet de commande **Move-CsUser** .

## Pour vérifier que la réplication utilisateur est terminée

1.  Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Cliquez sur le menu **Démarrer** , puis sur **Exécuter** .

3.  Entrez **eventvwr.exe** , puis cliquez sur **OK** .

4.  Dans l’Observateur d’événements, cliquez sur **Journaux des applications et des services** pour développer l’élément, puis sélectionnez Lync Server.

5.  Dans le volet **Actions** , cliquez sur **Filtrer le journal actuel** .

6.  Dans la liste **Sources d’événements** , cliquez sur **LS User Replicator** .

7.  Dans **\<Tous les ID d’événements\>** , entrez **30024** , puis cliquez sur **OK** .

8.  Dans la liste d’événements filtrés, sous l’onglet **Général** , recherchez une entrée qui indique que la réplication utilisateur s’est terminée avec succès.

