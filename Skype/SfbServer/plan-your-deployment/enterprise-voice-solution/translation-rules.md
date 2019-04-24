---
title: Règles de traduction dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: En savoir plus sur les règles de traduction et de numérotation de normalisation de chaînes dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 5b609701779a80645061036fd04e4a46427261b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206458"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Règles de traduction dans Skype pour Business Server

En savoir plus sur les règles de traduction et de numérotation de normalisation de chaînes dans Skype pour Business Server Enterprise Voice.

 Voix entreprise requiert que toutes les chaînes de numérotation normaliser au format E.164 pour effectuer la recherche inversée de numéros (RNL). Règles de traduction sont prises en charge pour les numéros appelés et les numéros d’appel. Thetrunk égal (c'est-à-dire, la passerelle associée, autocommutateur privé (PBX) ou jonction SIP) peut exiger que les numéros être dans un format de numérotation local. Pour convertir les numéros du format E.164 au format de numérotation local, vous pouvez définir une ou plusieurs règles de conversion pour manipuler l’URI demandé avant de l’acheminer vers l’homologue de jonction. Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».

En effectuant une conversion de l’itinéraire sortant sur le serveur, vous pouvez réduire les exigences de configuration sur chaque homologue de jonction afin de convertir les numéros de téléphone dans un format de numérotation local. Lorsque vous planifiez les passerelles et combien, à associer à un cluster de serveur de médiation spécifique, il peut être utile d’homologues de jonction de groupe locale similaire exigences de numérotation. En effet, cela peut réduire le nombre de règles de conversion requises et le temps nécessaire pour les rédiger.

> [!IMPORTANT]
> Association d’une ou plusieurs règles de traduction à une configuration de jonction Enterprise Voice doit être utilisé en guise d’alternative à la configuration des règles de traduction sur l’homologue de jonction. N’associez pas les règles de traduction à une configuration de jonction Enterprise Voice si vous avez configuré les règles de traduction sur l’homologue de jonction, car les deux règles peuvent entrer en conflit.

## <a name="example-translation-rules"></a>Exemples de règles de conversion

Les exemples de règles de conversion suivantes vous montrent comment développer des règles sur le serveur pour convertir des numéros du format E.164 au format local pour un homologue de jonction.

Pour plus d’informations sur l’implémentation des règles de conversion, reportez-vous à [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) dans la documentation de déploiement.

|**Description**|**Chiffres de début**|**Longueur**|**Chiffres à supprimer**|**Chiffres à ajouter**|**Modèle de correspondance**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Numérotation longue distance conventionnelle aux États-Unis  <br/> (signe les '+')  <br/> |+1  <br/> |12 exactement  <br/> |1  <br/> |0  <br/> |^\+(1\d{10}) $  <br/> |$1  <br/> |+14255551010 devient 14255551010  <br/> |
|Numérotation longue distance internationale aux États-Unis  <br/> (supprimer le signe '+' et ajouter 011)  <br/> |+  <br/> |11 au moins  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d+)$  <br/> |011$1  <br/> |+441235551010 devient 011441235551010  <br/> |


