---
title: Règles de conversion dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: En savoir plus sur les règles de traduction et de composer la normalisation de chaînes dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: ff3718e89d152a2b6c7d1c78ccaaa055d00ffcdb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="translation-rules-in-skype-for-business-server-2015"></a>Règles de conversion dans Skype Entreprise Server 2015
 
En savoir plus sur les règles de traduction et de composer la normalisation de chaînes dans Skype pour Business Server Voix Entreprise.
  
 Voix Entreprise requiert que toutes les chaînes de connexion à être normalisé au format E.164 pour effectuer la recherche de numéro inversée (RNL). Règles de traduction sont pris en charge pour les numéros appelés et les numéros d’appel. Homologue de Thetrunk (c'est-à-dire, la passerelle associée, autocommutateur privé (PBX) ou SIP trunk) peut-être exiger que les numéros soient dans un format de numérotation locale. Pour convertir les numéros du format E.164 au format de numérotation local, vous pouvez définir une ou plusieurs règles de conversion pour manipuler l’URI demandé avant de l’acheminer vers l’homologue de jonction. Par exemple, vous pouvez rédiger une règle pour supprimer la valeur « +44 » au début de la chaîne de numérotation et la remplacer par « 0144 ».
  
En effectuant une conversion de l’itinéraire sortant sur le serveur, vous pouvez réduire les exigences de configuration sur chaque homologue de jonction afin de convertir les numéros de téléphone dans un format de numérotation local. Lorsque vous planifiez les passerelles et combien, à associer à un cluster de serveur de médiation spécifique, il peut être utile pour homologues de tronc de groupe avec des locaux similaire des exigences de numérotation. En effet, cela peut réduire le nombre de règles de conversion requises et le temps nécessaire pour les rédiger.
  
> [!IMPORTANT]
> Associer une ou plusieurs règles de traduction avec une configuration de jonction de Voix Entreprise doit être utilisé comme alternative à la configuration des règles de traduction sur l’homologue du tronc. N’associez pas les règles de traduction à une configuration de jonction de Voix Entreprise si vous avez configuré des règles de traduction sur l’homologue du tronc, car les deux règles peuvent entrer en conflit. 
  
## <a name="example-translation-rules"></a>Exemples de règles de conversion

Les exemples de règles de conversion suivantes vous montrent comment développer des règles sur le serveur pour convertir des numéros du format E.164 au format local pour un homologue de jonction.
  
Pour plus d’informations sur la façon d’implémenter des règles de traduction, consultez [Définition des règles de traduction](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) de la documentation sur le déploiement.
  
|**Description**|**Premiers chiffres**|**Longueur**|**Chiffres à supprimer**|**Chiffres à ajouter**|**Modèle de correspondance**|**Conversion**|**Exemple**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Numérotation longue distance conventionnelle aux États-Unis  <br/> (retirer le '+')  <br/> |+ 1  <br/> |12 exactement  <br/> |1  <br/> |0  <br/> |^\+(1\d {10}) $  <br/> |$1  <br/> |+14255551010 devient 14255551010  <br/> |
|Numérotation longue distance internationale aux États-Unis  <br/> (supprimer les '+' et ajouter 011)  <br/> |+  <br/> |11 au moins  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d+)$  <br/> |011$1  <br/> |+441235551010 devient 011441235551010  <br/> |
   

