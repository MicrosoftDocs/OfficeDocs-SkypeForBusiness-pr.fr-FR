---
title: "Lync Server 2013 : Vérif. des règles de normalisation pour le parcage d’appel"
TOCTitle: Vérification des règles de normalisation pour le parcage d’appel
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398981(v=OCS.15)
ms:contentKeyID: 49299064
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification des règles de normalisation pour le parcage d’appel dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-11_

Les orbites de parcage d’appel ne doivent pas être normalisées. Vérifiez sur vos plans de numérotation que vos numéros orbites ne sont pas normalisés. Si vous devez créer une règle de normalisation supplémentaire pour empêcher la normalisation de vos orbites, suivez la procédure de la section [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md) pour définir une nouvelle règle de normalisation afin que le **modèle à suivre** identifie la plage d’orbites et que le **modèle de conversion** affiche la valeur **$1**. Par exemple, si votre plage d’orbites de parcage d’appel s’étend de 7000 à 7999, le champ **Modèle à suivre** affiche **^(7\\d{3})$** et **Modèle de conversion** **$1**.

> [!IMPORTANT]  
> Vérifiez que la règle de normalisation par défaut de vos plans de numérotation ne contient pas l’élément <strong>^(\d*)</strong>. Sinon, votre règle de normalisation de parcage d’appel ne sera jamais exécutée.

## Voir aussi

#### Tâches

[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

