---
title: "Lync Server 2013 : Pub. des mod. en att. de la conf. du routage des comm. Voc."
TOCTitle: Publication des modifications en attente de la configuration du routage des communications vocales
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413088(v=OCS.15)
ms:contentKeyID: 49299461
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-08-07_

Après avoir modifié les paramètres de configuration dans les pages du groupe **Routage des communications vocales** , effectuez cette procédure pour consulter, publier ou annuler les modifications en attente.

> [!IMPORTANT]  
> Vérifiez qu’un seul utilisateur à la fois modifie les paramètres de configuration du routage des communications vocales.<br />
Toutes les modifications en attente doivent être publiées en même temps en exécutant la commande <strong>Valider tout</strong> . Vous ne pouvez pas sélectionner les modifications en attente que vous voulez publier. Avant de publier les modifications en attente, exécutez la commande <strong>Vérifier les modifications non validées</strong> et annulez les modifications de configuration que vous ne voulez pas publier.<br />
Si vous quittez les pages du groupe <strong>Routage des communications vocales</strong> avant d’avoir validé les modifications en attente, toutes les modifications en attente seront perdues. Cependant, vous pouvez exporter la configuration en cours (dont les modifications en attente) vers un fichier de configuration des communications vocales, puis importer et publier la configuration mise à jour. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-export-a-voice-route-configuration-file.md">Exportation d’un fichier de configuration d’itinéraire des communications vocales dans Lync Server 2013</a>.

## Pour consulter, publier ou annuler les modifications de la configuration du routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales** .

4.  Effectuez les modifications souhaitées au niveau de la configuration sur chacune des pages du groupe **Routage des communications vocales** .

5.  Pour consulter les modifications en attente sans les publier, sélectionnez **Vérifier les modifications non validées** dans le menu **Valider** .

6.  Si vous souhaitez annuler l’une des modifications en attente, effectuez l’une des opérations suivantes :
    
      - Sélectionnez **Annuler toutes les modifications non validées** dans le menu **Valider** .
    
      - Accédez à l’onglet de la page **Routage des communications vocales** où se trouvent les modifications en attente que vous souhaitez annuler, cliquez sur **Valider** , puis sur **Annuler les modifications sélectionnées** .

7.  Une fois que vous avez passé en revue toutes les modifications en attente et annulé celles que vous ne souhaitez pas publier, cliquez sur **Valider** , puis sur **Valider tout** .

8.  Dans la boîte de dialogue **Paramètres de configuration de la voix non validés** qui affiche la liste de toutes les modifications en attente, cliquez sur **OK** .
    
    Lorsque le Panneau de configuration Lync Server a validé les modifications, le message **La publication de la configuration du routage des communications vocales a réussi** s’affiche.

