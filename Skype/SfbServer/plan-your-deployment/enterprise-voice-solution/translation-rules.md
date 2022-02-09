---
title: Règles de traduction dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Découvrez les règles de traduction et la normalisation des chaînes de numérotation dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: c2cc7990a0b3c61ef11e20fbc43b678a841d8137
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403743"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Règles de traduction dans Skype Entreprise Server

Découvrez les règles de traduction et la normalisation des chaînes de numérotation dans Skype Entreprise Server Voix Entreprise.

 Voix Entreprise exige que toutes les chaînes de numérotation adoptent le format standard E.164 pour des besoins de recherche de numéros inverse. Les règles de traduction sont pris en charge à la fois pour les numéros appelés et les numéros d’appel. L’homologue de connexion (c’est-à-dire, la passerelle associée, le PBX (private branch exchange) ou la connexion SIP) peut exiger que les numéros soient au format de numérotation local. Pour traduire des numéros du format E.164 vers un format de numérotation local, vous pouvez définir une ou plusieurs règles de traduction pour manipuler l’URI de demande avant de l’router vers l’homologue de la connexion. Par exemple, vous pouvez rédiger une règle de traduction pour remplacer « +44 » au début de la chaîne de numérotation par « 0144 ».

En faisant une traduction de l’itinéraire sortant sur le serveur, vous pouvez réduire les exigences de configuration sur chaque homologue de ligne afin de traduire les numéros de téléphone dans un format de numérotation local. Lorsque vous planifiez les passerelles et le nombre de passerelles à associer à un cluster de serveurs de médiation spécifique, il peut s’avérer utile de regrouper des homologues de trunk avec des exigences de numérotation locale similaires. Cela peut réduire le nombre de règles de traduction requises et le temps nécessaire pour les écrire.

> [!IMPORTANT]
> L’association d’une ou de plusieurs règles de traduction à une configuration de Voix Entreprise doit être utilisée comme alternative à la configuration des règles de traduction sur l’homologue de la trunk. N’associez pas de règles de traduction à une configuration de Voix Entreprise si vous avez configuré des règles de traduction sur l’homologue de la trunk, car les deux règles peuvent être en conflit.

## <a name="example-translation-rules"></a>Exemples de règles de traduction

Les exemples de règles de traduction suivants montrent comment développer des règles sur le serveur pour traduire des nombres du format E.164 au format local pour l’homologue de la trunk.

Pour plus d’informations sur l’implémentation des règles de traduction, voir [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in the Deployment documentation.

|**Description**|**Chiffres de début**|**Length**|**Chiffres à supprimer**|**Chiffres à ajouter**|**Modèle de correspondance**|**Traduction**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Appels longue distance classiques aux États-Unis  <br/> (dénudez le « + » )  <br/> |+1  <br/> |Exactement 12  <br/> |1  <br/> |0  <br/> |^\+(1\d{10}) $  <br/> |$1  <br/> |+14255551010 devient 14255551010  <br/> |
|Numérotation longue distance internationale aux États-Unis  <br/> (bandez « + » et ajoutez 011)  <br/> |+  <br/> |Au moins 11  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d+)$  <br/> |011$1  <br/> |+441235551010 devient 011441235551010  <br/> |