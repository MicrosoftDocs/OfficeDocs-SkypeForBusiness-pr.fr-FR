---
title: Rapport de liste des échecs dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Résumé : Découvrez le Failure List Report dans Skype pour Business Server 2015.'
ms.openlocfilehash: 7cb146569958908e79700e725d473bc246295c9d
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569319"
---
# <a name="failure-list-report-in-skype-for-business-server-2015"></a>Rapport de liste des échecs dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez le Failure List Report dans Skype pour Business Server 2015.
  
Le Rapport des listes d’échecs fournit des informations sur les participants individuels à une session P2P ou session de conférence ayant échoué. Ces informations incluent l’URI de l’utilisateur qui a rencontré le problème, ainsi que le code de réponse SIP et l’ID de diagnostic associés à l’échec.
  
## <a name="accessing-the-failure-list-report"></a>Accès au Rapport des listes d’échecs

Le rapport liste des défaillances est accessible en cliquant sur une des mesures suivantes dans le [Rapport de répartition dans Skype pour Business Server 2015](failure-distribution-report.md):
  
- Motifs de diagnostic principaux (sessions)
    
- Modalités principales (sessions)
    
- Pools principaux (sessions)
    
- Sources principales (sessions)
    
- Composants principaux (sessions)
    
- Utilisateurs émetteurs principaux (sessions)
    
- Utilisateurs destinataires principaux (sessions)
    
- Agents utilisateurs émetteurs principaux (sessions)
    
Dans le rapport liste des défaillances, vous pouvez accéder le [rapport détaillé de Session d’égal à égal dans Skype pour Business Server 2015](peer-to-peer-session-detail-report.md) en cliquant sur la mesure détail de Session pour une session d’égal à égal. Vous pouvez également accéder au Rapport détaillé de conférence en cliquant sur la mesure Conférence pour une conférence.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Exploitation optimale du Rapport des listes d’échecs

Le Rapport des listes d’échecs vous permet d’afficher une description de chaque code de réponse ou de chaque ID de diagnostic en maintenant simplement la souris au-dessus de la valeur concernée. Par exemple, si vous maintenez la souris au-dessus de l’ID de diagnostic 7025, les informations suivantes s’affichent dans une info-bulle :
  
Erreur du serveur interne lors de la création du média pour l’utilisateur.
  
Il est important de noter que le Rapport des listes d’échecs ne fournit pas une méthode simple de récupérer directement une liste de tous les utilisateurs qui ont participé à au moins une session ayant échoué, et qu’il ne permet pas non plus de déterminer les utilisateurs qui sont le plus souvent impliqués dans une session ayant échoué. (Pour une chose, le Failure List Report ne possède aucuns possibilités de filtrage) Toutefois, si vous exportez les données, puis la convertir un fichier de valeurs séparées par des virgules, vous pouvez utiliser Windows PowerShell pour trouver les réponses aux questions telles que celles. Par exemple, supposons que vous enregistrez les données dans un fichier .CSV nommé C:\Data\Failure_List.csv. En fonction des données enregistrées dans ce fichier, la commande suivante répertorie tous les utilisateurs qui ont été impliqués dans au moins une session ayant échoué : 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Cette commande renvoie une liste semblable à ceci :
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Les deux commandes suivantes renvoient le nombre total de sessions ayant échoué dans lesquelles chaque utilisateur a été impliqué :
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Des données semblables à ceci sont renvoyées :
  
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
  
**Mesures du rapport de liste des échecs**

|**Nom**|**Vous pouvez trier sur cet élément ?**|**Description**|
|:-----|:-----|:-----|
|**Heure du rapport** <br/> |Non  <br/> |Date et heure d’enregistrement du rapport.  <br/> |
|**Demande** <br/> |Non  <br/> |Type de demande SIP ayant échoué. Par exemple, INVITE ou BYE.  <br/> |
|**Code de réponse** <br/> |Non  <br/> |Code de réponse SIP envoyé lors de l’échec de conférence.  <br/> |
|**ID de diagnostic** <br/> |Non  <br/> |Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs.  <br/> |
|**Coût/temps de connexion (ms)** <br/> |Non  <br/> |Temps (en millisecondes) requis pour que l’utilisateur rejoigne la conférence.  <br/> |
|**De l’utilisateur** <br/> |Non  <br/> |Adresse SIP de l’utilisateur qui a initié l’appel.  <br/> |
|**Agent utilisateur d’origine** <br/> |Non  <br/> |Logiciel utilisé par le point de terminaison de l’utilisateur ayant initié l’appel.  <br/> |
|**À l’utilisateur** <br/> |Non  <br/> |Adresse IP de l’utilisateur qui était appelé.  <br/> |
   

