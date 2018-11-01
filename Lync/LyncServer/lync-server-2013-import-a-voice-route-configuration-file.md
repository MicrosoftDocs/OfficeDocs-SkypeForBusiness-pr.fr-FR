---
title: "Lync Server 2013 : Imp. d’un fichier de conf. d’itinéraire de comm. vocales"
TOCTitle: Importation d’un fichier de configuration d’itinéraire de communications vocales
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398301(v=OCS.15)
ms:contentKeyID: 49297127
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importation d’un fichier de configuration d’itinéraire de communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Si vous souhaitez enregistrer la configuration du routage des communications vocales sans la publier, suivez ces étapes pour utiliser les commandes d’importation et d’exportation de la configuration du Panneau de configuration Lync Server afin d’enregistrer et de récupérer une capture instantanée de votre configuration. Lorsque vous importez un fichier de configuration du routage des communications vocales (.vcfg) mais que cette configuration a été entre temps modifiée sur le serveur, les pages qui figurent dans le groupe **Routage de communications vocales** du Panneau de configuration Lync Server indiquent que des modifications non validées ont été apportées au routage de communications vocales. Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.

Si vous avez modifié les paramètres sur une page du groupe sans les valider, ces modifications sont enregistrées dans le fichier de configuration des communications vocales exporté (.vcfg). Ainsi, vous pouvez modifier la configuration du routage des communications vocales dans le cadre de plusieurs sessions avant de publier les modifications.

## Pour importer une configuration du routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Dans le menu **Actions**, cliquez sur **Importer la configuration**.

5.  Recherchez le fichier de configuration que vous voulez importer, puis cliquez sur **Ouvrir**.

6.  Cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Exportation d’un fichier de configuration d’itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

