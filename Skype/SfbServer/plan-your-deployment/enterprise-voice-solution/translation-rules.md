---
title: Règles de traduction dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Découvrez les règles de traduction et la normalisation des chaînes de numérotation dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 0c00776dae502bfd28bbe27e90012fabb6e25c93
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802684"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Règles de traduction dans Skype Entreprise Server

Découvrez les règles de traduction et la normalisation des chaînes de numérotation dans Skype Entreprise Server Voix Entreprise.

 Voix Entreprise exige que toutes les chaînes de numérotation adoptent le format standard E.164 pour des besoins de recherche de numéros inverse. Les règles de traduction sont pris en charge pour les numéros appelés et les numéros d’appel. L’homologue de connexion (c’est-à-dire, la passerelle associée, le PBX (private branch exchange) ou la connexion SIP) peut exiger que les numéros soient au format de numérotation local. Pour traduire des numéros du format E.164 vers un format de numérotation local, vous pouvez définir une ou plusieurs règles de traduction pour manipuler l’URI de demande avant de l’router vers l’homologue de la liaison. Par exemple, vous pouvez rédiger une règle de traduction pour remplacer « +44 » au début de la chaîne de numérotation par « 0144 ».

En faisant une traduction de l’itinéraire sortant sur le serveur, vous pouvez réduire les exigences de configuration sur chaque homologue de ligne afin de traduire les numéros de téléphone dans un format de numérotation local. Lorsque vous planifiez les passerelles et le nombre de passerelles à associer à un cluster de serveurs de médiation spécifique, il peut s’avérer utile de regrouper des homologues de trunk avec des exigences de numérotation locale similaires. Cela peut réduire le nombre de règles de traduction requises et le temps nécessaire pour les écrire.

> [!IMPORTANT]
> L’association d’une ou de plusieurs règles de traduction à une configuration de Voix Entreprise doit être utilisée comme alternative à la configuration des règles de traduction sur l’homologue de la trunk. N’associez pas de règles de traduction à une configuration de Voix Entreprise si vous avez configuré des règles de traduction sur l’homologue de la trunk, car les deux règles peuvent être en conflit.

## <a name="example-translation-rules"></a>Exemples de règles de traduction

Les exemples de règles de traduction suivants montrent comment développer des règles sur le serveur pour traduire des nombres du format E.164 au format local pour l’homologue de la trunk.

Pour plus d’informations sur l’implémentation des règles de traduction, voir [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.

|**Description**|**Chiffres de début**|**Length**|**Chiffres à supprimer**|**Chiffres à ajouter**|**Modèle de correspondance**|**Traduction**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Appels longue distance classiques aux États-Unis  <br/> (dénudez le « + » )  <br/> |+1  <br/> |Exactement 12  <br/> |1   <br/> |0  <br/> |^\+(1\d {10} ) $  <br/> |$1  <br/> |+14255551010 devient 14255551010  <br/> |
|Numérotation longue distance internationale aux États-Unis  <br/> (bandez « + » et ajoutez 011)  <br/> |+  <br/> |Au moins 11  <br/> |1   <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 devient 011441235551010  <br/> |


