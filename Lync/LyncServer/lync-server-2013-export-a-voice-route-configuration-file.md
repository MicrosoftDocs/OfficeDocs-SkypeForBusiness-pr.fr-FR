---
title: "Lync Server 2013 : Exp. d’un fichier de conf. d’itinéraire des comm. Voc."
TOCTitle: Exportation d’un fichier de configuration d’itinéraire des communications vocales
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398081(v=OCS.15)
ms:contentKeyID: 49296079
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportation d’un fichier de configuration d’itinéraire des communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Si vous souhaitez enregistrer la configuration du routage des communications vocales sans la publier, suivez ces étapes pour utiliser les commandes d’importation et d’exportation de la configuration du Panneau de configuration Lync Server afin d’enregistrer et de récupérer une capture instantanée de votre configuration. Lorsque vous importez un fichier de configuration du routage des communications vocales (.vcfg) mais que cette configuration a été entre temps modifiée sur le serveur, les pages qui figurent dans le groupe **Routage de communications vocales** du Panneau de configuration Lync Server indiquent que des modifications non validées ont été apportées au routage de communications vocales. Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.

Si vous avez modifié les paramètres sur une page du groupe sans les valider, ces modifications sont enregistrées dans le fichier de configuration des communications vocales exporté (.vcfg). Ainsi, vous pouvez modifier la configuration du routage des communications vocales dans le cadre de plusieurs sessions avant de publier les modifications.

## Pour exporter une configuration du routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales** .

4.  Dans le menu **Actions** , cliquez sur **Exporter la configuration** .

5.  Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.

## Voir aussi

#### Tâches

[Importation d’un fichier de configuration d’itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-import-a-voice-route-configuration-file.md)

