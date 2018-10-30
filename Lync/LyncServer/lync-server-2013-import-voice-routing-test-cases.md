---
title: "Lync Server 2013 : Import. des cas de test de routage des comm. voc."
TOCTitle: Importation des cas de test de routage des communications vocales
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398460(v=OCS.15)
ms:contentKeyID: 49297428
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importation des cas de test de routage des communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Les cas de test vous permettent de tester les itinéraires des communications vocales dans votre organisation : vous devez pour cela définir le numéro à composer ainsi que le plan de numérotation et la stratégie de la voix à employer. Lync Server 2013 peut alors vérifier que, selon ces conditions, le numéro fourni peut être acheminé vers le réseau RTC.

Les cas de test, créés à l’aide du Panneau de configuration Lync Server, sont en général enregistrés uniquement sur le serveur où ils ont été créés et exécutés. Cependant, il est possible d’exporter ces cas de test sous forme de fichiers XML (avec l’extension .vtest) et de les importer sur d’autres serveurs. Vous pouvez ainsi exécuter les mêmes tests sur différents ordinateurs situés à différents endroits de votre topologie.

## Pour importer un cas de test de routage des communications vocales

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Dans le menu **Actions**, cliquez sur **Importer des cas de test**.

5.  Recherchez le fichier de cas de test (.vtest) que vous voulez importer, puis cliquez sur **Ouvrir**.

6.  Cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > Chaque fois que vous importez un fichier .vtest, vous devez exécuter la commande <strong>Valider tout</strong> pour publier le cas de test. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Exportation des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)

