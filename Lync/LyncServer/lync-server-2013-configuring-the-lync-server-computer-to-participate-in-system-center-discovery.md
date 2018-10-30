---
title: "Conf. de l’ordinateur Lync Server pour la particip. à la déc. de System Center"
TOCtitle: "Conf. de l’ordinateur Lync Server pour la particip. à la déc. de System Center"
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204776(v=OCS.15)
ms:contentKeyID: 49296756
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de l’ordinateur Lync Server pour la participation à la découverte de System Center

 

_**Dernière rubrique modifiée :** 2012-10-20_

Pour vous assurer que votre nouvel agent Lync Server participe au processus de découverte du System Center Operations Manager, vous devez appliquer la procédure suivante sur chaque ordinateur sur lequel a été installée la console System Center Operations Manager :

1.  Sous l’onglet **Administration**, cliquez sur **Géré par agent**.

2.  Cliquez avec le bouton droit sur le nom de l’ordinateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue **Propriétés**, sous l’onglet **Sécurité**, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.

Une fois l’étape 2 terminée, redémarrez le service Agent d’intégrité. (Le redémarrage du service va « forcer » la découverte du nouvel ordinateur. Si vous ne redémarrez pas le service, la découverte du nouvel ordinateur par le System Center Operations Manager peut prendre jusqu’à 4 heures.). Une fois le service redémarré, vérifiez qu’aucun événement d’erreur n’a été enregistré dans le journal des événements Operations Manager sur cet ordinateur.

