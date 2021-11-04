---
title: Rapport des listes d’échecs Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Résumé : Découvrez le rapport des listes d’échecs Skype Entreprise Server.'
ms.openlocfilehash: 6853da551f65de835f6966cf0a59af57d80e1f75
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763632"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Rapport des listes d’échecs Skype Entreprise Server 
 
**Résumé :** Découvrez le rapport des listes d’échecs Skype Entreprise Server.
  
Le Rapport des listes d’échecs fournit des informations sur les participants individuels à une session d’égal à égal ou session de conférence ayant échoué. Ces informations incluent l’URI de l’utilisateur qui a rencontré le problème, ainsi que le code de réponse SIP et l’ID de diagnostic associés à l’échec.
  
## <a name="accessing-the-failure-list-report"></a>Accès au Rapport des listes d’échecs

Le rapport des listes d’échecs est accessible en cliquant sur l’une des mesures suivantes dans le rapport de répartition des [défaillances Skype Entreprise Server](failure-distribution-report.md):
  
- Motifs de diagnostic principaux (sessions)
    
- Modalités principales (sessions)
    
- Pools principaux (sessions)
    
- Sources principales (sessions)
    
- Composants principaux (sessions)
    
- Utilisateurs émetteurs principaux (sessions)
    
- Utilisateurs destinataires principaux (sessions)
    
- Agents utilisateurs émetteurs principaux (sessions)
    
À partir du rapport des listes d’échecs, vous pouvez accéder au rapport détaillé de session P2E dans [Skype Entreprise Server](peer-to-peer-session-detail-report.md) en cliquant sur la mesure Détails de session pour une session d’égal à égal. Vous pouvez également accéder au Rapport détaillé de conférence en cliquant sur la mesure Conférence pour une conférence.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Exploitation optimale du Rapport des listes d’échecs

Le Rapport des listes d’échecs vous permet d’afficher une description de chaque code de réponse ou de chaque ID de diagnostic en maintenant simplement la souris au-dessus de la valeur concernée. Par exemple, si vous maintenez la souris au-dessus de l’ID de diagnostic 7025, les informations suivantes s’affichent dans une info-bulle :
  
Erreur du serveur interne lors de la création du média pour l’utilisateur.
  
Il est important de noter que le Rapport des listes d’échecs ne fournit pas une méthode simple de récupérer directement une liste de tous les utilisateurs qui ont participé à au moins une session ayant échoué, et qu’il ne permet pas non plus de déterminer les utilisateurs qui sont le plus souvent impliqués dans une session ayant échoué. (Le Rapport des listes d’échecs ne dispose notamment pas de fonctionnalités de filtrage.) Toutefois, si vous exportez les données, puis que vous les convertissez en un fichier de valeurs séparées par des virgules, vous pouvez utiliser Windows PowerShell pour trouver les réponses à des questions de ce type. Par exemple, supposons que vous enregistrez les données dans un fichier .CSV nommé C:\Data\Failure_List.csv. En fonction des données enregistrées dans ce fichier, la commande suivante répertorie tous les utilisateurs qui ont été impliqués dans au moins une session ayant échoué : 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Cette commande retourne une liste semblable à ceci :
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Les deux commandes suivantes retournent le nombre total de sessions ayant échoué dans lesquelles chaque utilisateur a été impliqué :
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Des données semblables à ceci sont alors retournées :
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>Filtres

Aucun. Il est impossible de filtrer le Rapport des listes d’échecs.
  
## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le Rapport des listes d’échecs pour chaque appel ayant échoué.
  
**Mesures du Rapport des listes d’échecs**

|**Name**|**Est-il possible d’effectuer un tri sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Heure du rapport** <br/> |Non  <br/> |Date et heure d’enregistrement du rapport.  <br/> |
|**Demande** <br/> |Non  <br/> |Type de demande SIP ayant échoué. Par exemple, INVITE ou BYE.  <br/> |
|**Code de réponse** <br/> |Non  <br/> |Code de réponse SIP envoyé lors de l’échec de conférence.  <br/> |
|**ID de diagnostic** <br/> |Non  <br/> |Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.  <br/> |
|**Coût/temps de connexion (ms)** <br/> |Non  <br/> |Temps (en millisecondes) requis pour que l’utilisateur rejoigne la conférence.  <br/> |
|**De l’utilisateur** <br/> |Non  <br/> |Adresse SIP de l’utilisateur qui a initié l’appel.  <br/> |
|**Agent utilisateur d’origine** <br/> |Non  <br/> |Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié l’appel.  <br/> |
|**À l’utilisateur** <br/> |Non  <br/> |Adresse IP de l’utilisateur qui était appelé.  <br/> |
   

