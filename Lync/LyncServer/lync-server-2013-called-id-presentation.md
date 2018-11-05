---
title: Présentation de l’ID de la personne appelée dans Lync Server 2013
TOCTitle: Présentation de l’ID de la personne appelée dans Lync Server 2013
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49891548
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Présentation de l’ID de la personne appelée dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Avec Lync Server 2010, le numéro de téléphone du destinataire (numéro de téléphone appelé) peut être traduit du format E.164 au format de numérotation local requis par l’*homologue de jonction* (passerelle associée, système PBX ou jonction SIP). Pour ce faire, vous devez définir une ou plusieurs règles de traduction pour traduire l’URI de demande avant de l’acheminer vers l’homologue de jonction.

> [!IMPORTANT]  
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de jonction Voix Entreprise peut servir d’<em>alternative</em> à la définition de règles de traduction sur l’homologue de jonction. N’associez pas de règles de traduction avec une configuration de jonction Voix Entreprise si vous avez configuré les règles de traduction sur l’homologue de jonction, car les deux règles risqueraient de provoquer un conflit.

Vous pouvez employer l’une des méthodes suivantes pour créer ou modifier une règle de traduction :

  - Utilisez l’outil **Créer une règle de traduction** pour spécifier les valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et ceux à ajouter, puis laissez Panneau de configuration Lync Server générer pour vous le modèle correspondant et la règle de traduction.

  - Écrivez les expressions régulières manuellement pour définir le modèle correspondant et la règle de traduction.

> [!NOTE]  
> Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « Expressions régulières .NET Framework » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=140927&amp;clcid=0x40C</a>.

## Dans cette section

  - [Créer ou modifier une règle de traduction à l’aide de l’outil Créer une règle de traduction](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Créer ou modifier manuellement une règle de traduction](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

## Voir aussi

#### Concepts

[Présentation de l’ID d’appelant dans Lync Server 2013](lync-server-2013-caller-id-presentation.md)

