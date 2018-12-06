---
title: "Lync Server 2013 : Exp. des cas de test de routage des communications vocales"
TOCTitle: Exportation des cas de test de routage des communications vocales
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425957(v=OCS.15)
ms:contentKeyID: 49297097
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportation des cas de test de routage des communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les cas de test vous permettent de tester les itinéraires des communications vocales dans votre organisation : vous devez pour cela définir le numéro à composer ainsi que le plan de numérotation et la stratégie de la voix à employer. Lync Server peut alors vérifier que, selon ces conditions, le numéro fourni peut être acheminé vers le réseau RTC.

Les cas de test, créés à l’aide du Panneau de configuration Lync Server, sont en général enregistrés uniquement sur le serveur où ils ont été créés et exécutés. Cependant, il est possible d’exporter ces cas de test sous forme de fichiers XML (avec l’extension .vtest) et de les importer sur d’autres serveurs. Vous pouvez ainsi exécuter les mêmes tests sur différents ordinateurs situés à différents endroits de votre topologie.

## Pour exporter un cas de test de routage des communications vocales

1.  Dans le Panneau de configuration Lync Server, cliquez sur **Routage des communications vocales** , puis sur **Tester le routage des communications vocales** .

2.  Sous l’onglet **Tester le routage des communications vocales** , sélectionnez le cas de test (ou les cas de test) à exporter. Pour sélectionner plusieurs cas de test, cliquez sur le premier cas à exporter, puis maintenez la touche Ctrl enfoncée et sélectionnez les cas supplémentaires à exporter.

3.  Cliquez sur **Action** , puis sur **Exporter des cas de test** .

4.  Dans la boîte de dialogue **Enregistrer sous** , sélectionnez un dossier où stocker les cas de test, puis tapez le nom du fichier XML résultant dans la zone **Nom de fichier** . Notez que si vous exportez plusieurs cas de test, ces derniers sont tous enregistrés dans un fichier XML unique.

5.  Pour enregistrer les cas de test, cliquez sur **Enregistrer** .

## Voir aussi

#### Tâches

[Importation des cas de test de routage des communications vocales dans Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)

