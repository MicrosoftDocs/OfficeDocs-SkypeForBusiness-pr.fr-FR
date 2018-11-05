---
title: 'Lync Server 2013 : Définition de règles de normalisation'
TOCTitle: Définition de règles de normalisation
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399071(v=OCS.15)
ms:contentKeyID: 49299231
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de règles de normalisation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les règles de normalisation Lync Server 2013 utilisent des expressions régulières .NET Framework pour convertir les numéros de téléphone composés au format E.164. En d’autres termes, elles emploient le numéro de téléphone composé par un utilisateur et le convertissent au format utilisé en interne par Lync Server. Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.

Pour plus d’informations sur les règles de normalisation, reportez-vous à [Plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification.

Pour plus d’informations sur l’écriture des expressions régulières, reportez-vous à « Expressions régulières .NET Framework » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).

Vous pouvez utiliser l’une ou l’autre des méthodes suivantes pour définir ou modifier une règle de normalisation :

  - Utilisez l’outil **Créer une règle de normalisation** pour préciser les valeurs des chiffres de départ, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laissez Panneau de configuration Lync Server générer le modèle de correspondance et la règle de conversion pour vous.

  - Écrivez les expressions régulières manuellement pour définir le modèle correspondant et la règle de conversion.

## Dans cette section

  - [Création ou modification d’une règle de normalisation avec la section Création d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

## Voir aussi

#### Tâches

[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

