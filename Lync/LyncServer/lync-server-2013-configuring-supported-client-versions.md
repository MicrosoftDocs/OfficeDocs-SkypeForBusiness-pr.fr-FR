---
title: Configuration des versions du client prises en charge
TOCTitle: Configuration des versions du client prises en charge
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412832(v=OCS.15)
ms:contentKeyID: 49298547
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des versions du client prises en charge

 

_**Dernière rubrique modifiée :** 2012-12-14_

Dans Lync Server 2013, vous pouvez définir des stratégies de version du client afin de spécifier les versions des clients pris en charge dans votre environnement. De plus, vous pouvez utiliser la configuration de version globale du client afin de spécifier une action par défaut pour les clients ne disposant pas encore d’une stratégie de version définie, qui ne sont par conséquent ni pris en charge ni restreints de manière explicite.

Vous pouvez également utiliser des stratégies de version du client afin de gérer les mises à jour du client. Lorsque vous définissez une stratégie de version du client et que vous utilisez les options **Autoriser et mettre à niveau** et **Bloquer et mettre à niveau**, les clients reçoivent un logiciel mis à jour à partir du service Windows Server Update (si vous utilisez ce service) ou à partir de Windows Update.

## Paramètres de la stratégie de version de client

La stratégie de version de client par défaut nécessite que tous les clients exécutent Lync ou Microsoft Office Communicator 2007 R2. Si les clients de votre environnement exécutent déjà des versions précédentes de Communicator, vous devrez peut-être reconfigurer les règles de version de client pour empêcher les clients et les périphériques d’être bloqués ou mis à jour de manière inopinée lors de la connexion à Lync Server 2013. Vous pouvez modifier la règle par défaut ou la remplacer par une règle supérieure dans la liste des stratégies de version de client. De plus, à mesure que des mises à jour cumulées sont diffusées, vous devez configurer la stratégie de version de client pour demander les dernières mises à jour.

