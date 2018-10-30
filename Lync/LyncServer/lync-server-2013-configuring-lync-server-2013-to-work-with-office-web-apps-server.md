---
title: "Conf de Lync Server 2013 pour le fonctionnement avec Office Web Apps Server"
TOCtitle: "Conf de Lync Server 2013 pour le fonctionnement avec Office Web Apps Server"
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204944(v=OCS.15)
ms:contentKeyID: 49297399
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de Lync Server 2013 pour le fonctionnement avec Office Web Apps Server

 

_**Dernière rubrique modifiée :** 2013-04-22_

Avant de configurer Lync Server 2013 de manière à utiliser Office Web Apps Server, vous devez déployer et configurer Office Web Apps Server. Voir le document **Guide de déploiement d’Office Web Apps Server et d’Office Web Apps** pour obtenir des informations détaillées sur la façon d’installer et de configurer un serveur Office Web Apps unique ou pour obtenir des informations sur la façon d’installer et de configurer une batterie de serveurs Office Web Apps Server en vue d’une haute disponibilité.

Une fois Office Web Apps Server installé et votre batterie de serveurs web correctement configurée, vous devez ensuite configurer Lync Server pour communiquer avec le nouveau serveur. Pour cela, ajoutez l’URL de découverte d’Office Web Apps Server à votre topologie Lync Server. Pour ajouter Office Web Apps Server à votre topologie, procédez comme suit :

1.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

2.  Dans la boîte de dialogue **Générateur de topologie**, sélectionnez **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.

3.  Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom de votre document de topologie (par exemple, **PreWebAppsServerTopology**) dans la zone **Nom du fichier**, puis cliquez sur **Enregistrer**. Vous pouvez par la suite récupérer et republier cette topologie si vous rencontrez des problèmes avec votre nouvelle topologie.

4.  Dans le Générateur de topologie, développez successivement **Lync Server 2013**, le nom de votre site, **Pools frontaux Enterprise Edition**, puis cliquez avec le bouton droit sur l’un de vos pools et cliquez sur **Modifier les propriétés**.

5.  Dans la boîte de dialogue **Modifier les propriétés**, sous l’onglet **Général**, recherchez l’en-tête **Serveur Office Web Apps associé**, puis cliquez sur **Nouveau** (ou sélectionnez un serveur Office Web Apps Server existant dans la liste déroulante).

6.  Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, tapez le nom de domaine complet de votre ordinateur Office Web Apps Server dans la zone **Nom de domaine complet du serveur Office Web Apps**. L’URL de découverte du serveur Office Web Apps Server est alors automatiquement entrée dans la zone **URL de découverte du serveur Office Web Apps**.
    
    Si le serveur Office Web Apps Server est installé sur site et dans la même zone réseau que Lync Server 2013, l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)** ne doit pas être sélectionnée.
    
    Si le serveur Office Web Apps Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez alors l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)**.

7.  Dans la boîte de dialogue **Définir un nouveau serveur Office Web Apps**, cliquez sur **OK**. Ensuite, cliquez sur **OK** dans la boîte de dialogue **Modifier les propriétés**. L’URL de découverte d’Office Web Apps doit alors figurer parmi les associations du pool.

Vous devez répéter ce processus pour chaque pool à associer à votre serveur Office Web Apps Server.

Après avoir ajouté l’URL de découverte à la topologie, vous devez ensuite publier cette topologie mise à jour. Pour cela, dans le Générateur de topologie :

1.  Cliquez sur **Action**, puis sur **Publier la topologie**.

2.  Dans l’Assistant Publication de la topologie, dans la page **Publier la topologie**, cliquez sur **Suivant**.

3.  Dans la page **Assistant Publication terminé**, cliquez sur **Terminer**.

4.  Fermez le Générateur de topologie.

