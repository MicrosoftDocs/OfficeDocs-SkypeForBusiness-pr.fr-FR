---
title: Règles de traduction dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: En savoir plus sur les règles de traduction et sur la normalisation de la numérotation des chaînes dans Skype entreprise Server Voice.
ms.openlocfilehash: 1f435db01b5b15c97ae577565e4ba43f5de554ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297364"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Règles de traduction dans Skype entreprise Server

En savoir plus sur les règles de traduction et sur la normalisation de la numérotation des chaînes dans Skype entreprise Server Voice.

 Voix entreprise nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL). Les règles de traduction sont prises en charge pour les numéros appelés et les numéros d’appel. Thetrunk homologue (autrement dit, la passerelle associée, le PBX ou le Trunk SIP) peut nécessiter que les numéros soient dans un format de numérotation local. Pour convertir les numéros du format E.164 au format de numérotation local, vous pouvez définir une ou plusieurs règles de conversion pour manipuler l’URI demandé avant de l’acheminer vers l’homologue de jonction. Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».

En effectuant une conversion de l’itinéraire sortant sur le serveur, vous pouvez réduire les exigences de configuration sur chaque homologue de jonction afin de convertir les numéros de téléphone dans un format de numérotation local. Lorsque vous planifiez les passerelles et le nombre de passerelles à associer à un cluster de serveurs de médiation spécifique, il est possible que les homologues de groupe puissent s’avérer utiles pour la numérotation locale. En effet, cela peut réduire le nombre de règles de conversion requises et le temps nécessaire pour les rédiger.

> [!IMPORTANT]
> L’Association d’une ou plusieurs règles de traduction à une configuration de Trunk voix entreprise doit être utilisée comme alternative à la configuration de règles de traduction sur l’homologue de Trunk. N’associez pas de règles de traduction à une configuration de Trunk vocale d’entreprise si vous avez configuré des règles de traduction sur l’homologue de Trunk, car les deux règles peuvent entrer en conflit.

## <a name="example-translation-rules"></a>Exemples de règles de conversion

Les exemples de règles de conversion suivantes vous montrent comment développer des règles sur le serveur pour convertir des numéros du format E.164 au format local pour un homologue de jonction.

Pour plus d’informations sur l’implémentation des règles de conversion, reportez-vous à [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) dans la documentation de déploiement.

|**Description**|**Chiffres de début**|**Longueur**|**Chiffres à supprimer**|**Chiffres à ajouter**|**Modèle correspondant**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Numérotation longue distance conventionnelle aux États-Unis  <br/> (en pointillés  <br/> |+1  <br/> |12 exactement  <br/> |1  <br/> |0,4  <br/> |^\+(1{10}  <br/> |$1  <br/> |+14255551010 devient 14255551010  <br/> |
|Numérotation longue distance internationale aux États-Unis  <br/> (strip "+" et ajouter 011)  <br/> |+  <br/> |11 au moins  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d +) $  <br/> |011$1  <br/> |+441235551010 devient 011441235551010  <br/> |


