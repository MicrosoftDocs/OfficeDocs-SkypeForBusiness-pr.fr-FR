---
title: Compteurs de performance de mobilité dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Résumé : Découvrez les compteurs de performance que vous pouvez utiliser pour surveiller les serveurs exécutant l’API Unified Communications Web API (UCWA) et le service de mobilité Skype entreprise Server MCX.'
ms.openlocfilehash: e9a3ade40694ef18e1022388d48838822d409625
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817763"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Compteurs de performance de mobilité dans Skype entreprise Server
 
**Résumé :** Apprenez-en davantage sur les compteurs de performance que vous pouvez utiliser pour surveiller les serveurs exécutant l’API Unified Communications Web API (UCWA) et le service de mobilité Skype entreprise Server MCX.
  
Les tableaux suivants répertorient les noms et descriptions des compteurs de performance que vous pouvez utiliser pour surveiller les serveurs exécutant l’API Unified Communications Web API (UCWA) et le service de mobilité Skype entreprise Server MCX. 
  
Le nom de la catégorie pour les compteurs dans la table UCWA est **ls : Web-UCWA**.
  
Le nom de la catégorie pour les compteurs dans le tableau Service de mobilité Mcx est **LS:WEB - Mobile Communication Service**.

> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
  
## <a name="performance-counters-for-ucwa"></a>Compteurs de performances pour UCWA

|Compteur|Description|
|:-----|:-----|
|Active Application Count  <br/> |Nombre d’applications en cours  <br/> |
|Active Application Sharing Modality Count  <br/> |Nombre actuel de modalités de partage d’applications  <br/> |
|Active Audio Modality Count  <br/> |Nombre actuel de modalités audio  <br/> |
|Active Data Collaboration Modality Count  <br/> |Nombre actuel de modalités de collaboration de données  <br/> |
|Active Directory Photo Get Latency (ms)  <br/> |Ce compteur montre le temps moyen (en millisecondes) nécessaire pour récupérer une photo du répertoire actif.  <br/> |
|Active Messaging Modality Count  <br/> |Nombre actuel de modalités de messagerie  <br/> |
|Active Panoramic Video Modality Count  <br/> |Nombre actuel de modalités de vidéo panoramique  <br/> |
|Active Pending Get Count  <br/> |Nombre de gets actifs en attente ; connexions au serveur conservées depuis longtemps  <br/> |
|Active Session Count  <br/> |Nombre actuel de points de terminaison enregistrés dans UCWA par application et le total  <br/> |
|Active User Instance Count  <br/> |Nombre d’instances utilisateur en cours  <br/> |
|Active User Instances without Application  <br/> |Nombre d’instances utilisateur en cours sans application  <br/> |
|Active Video Modality Count  <br/> |Nombre actuel de modalités vidéo  <br/> |
|Application Creation Requests Received/Second  <br/> |Taux par seconde de demandes de création d’application reçues  <br/> |
|AS MCU Join Failures  <br/> |Nombre d’échecs de connexion au service MCU AS  <br/> |
|AV MCU Join Failures  <br/> |Nombre d’échecs de connexion au service MCU audio/vidéo  <br/> |
|Average Application Startup Time (ms)  <br/> |Délai de démarrage moyen de l’application en millisecondes  <br/> |
|Average Lifetime for Session (ms)  <br/> |Durée de vie moyenne pour une session en millisecondes  <br/> |
|Data MCU Join Failures  <br/> |Nombre d’échecs de connexion au service MCU de données  <br/> |
|Exchange Contact Search Latency (ms)  <br/> |Ce compteur affiche le temps moyen (en millisecondes) nécessaire pour rechercher des contacts dans Exchange  <br/> |
|Exchange HD Photo Get Latency (ms)  <br/> |Ce compteur affiche le temps moyen (en millisecondes) nécessaire pour récupérer une photo HD d’Exchange  <br/> |
|HTTP 4xx Responses/Second  <br/> |Taux de réponses avec un code 4xx HTTP par seconde  <br/> |
|HTTP 5xx Responses/Second  <br/> |Taux de réponses avec un code 5xx HTTP par seconde  <br/> |
|IM MCU Join Failures  <br/> |Nombre d’échecs de connexion au service MCU de messagerie instantanée  <br/> |
|Number of Active Directory Photo Get Failures  <br/> |Nombre d’échecs de récupération de photos du répertoire actif  <br/> |
|Number of Contact Search failures  <br/> |Nombre total d’échecs de recherche de contacts dans Exchange  <br/> |
|Number of Deserialization Failures  <br/> |Nombre total d’échecs de désérialisation  <br/> |
|Nombre d’échecs de photo HD  <br/> |Nombre total d’échecs de récupération de photos HD depuis Exchange  <br/> |
|Over The Maximum Subscriptions Per Application  <br/> |Nombre de requêtes d’abonnement dépassant le nombre maximal autorisé par application  <br/> |
|Over The Maximum Subscriptions Per Batch  <br/> |Nombre de requêtes d’abonnement dépassant le nombre maximal autorisé par lot  <br/> |
|Presence Subscription Failures  <br/> |Nombre d’échecs d’abonnement de présence  <br/> |
|Registering Endpoint Failures  <br/> |Nombre d’échecs d’enregistrement de points de terminaison  <br/> |
|Requests Received/Second  <br/> |Taux de demandes reçues par seconde  <br/> |
|Requests Succeeded/Second  <br/> |Taux de demandes réussies par seconde (codes de réponse 2xx/3xx HTTP)  <br/> |
|Succeeded Create Application Requests/Second  <br/> |Taux de demandes de création d’application réussies par seconde  <br/> |
|Timed Out Pending Get Count  <br/> |Nombre de gets en attente ayant expiré  <br/> |
|Total Application Creation Requests Received  <br/> |Nombre total de demandes de création d’application reçues depuis le démarrage du service  <br/> |
|Total HTTP 4xx Responses  <br/> |Nombre total de réponses 4xx HTTP  <br/> |
|Total HTTP 5xx Responses  <br/> |Nombre total de réponses 5xx HTTP  <br/> |
|Total Requests Received on the Command Channel  <br/> |Nombre total de demandes reçues sur le canal de commande  <br/> |
|Total Requests Succeeded  <br/> |Nombre total de demandes réussies  <br/> |
|Total Sessions Initiated  <br/> |Nombre total de sessions initiées depuis le démarrage du service  <br/> |
|Total Sessions Terminated Because of Idle Timeout  <br/> |Nombre total de sessions terminées en raison d’un délai d’expiration d’inactivité  <br/> |
|Total Throttled Applications  <br/> |Nombre d’applications limitées  <br/> |
   
**Compteurs de performances pour le service de mobilité Mcx**

|**Compteur**|**Description**|
|:-----|:-----|
|Durée de vie moyenne d’une session en millisecondes  <br/> |Durée de vie moyenne pour une session en millisecondes  <br/> |
|Abonnements actuels aux notifications push  <br/> |Nombre actuel d’abonnements de notification push. Ce chiffre, associé au Nombre de sessions actuellement actives, représente le sous-ensemble de sessions actuellement actives enregistrées pour les appareils Windows Mobile ou iPhone.  <br/> |
|Nombre d’interrogations réseau expirées actuellement actives  <br/> |Nombre d’interrogations réseau dont le délai d’attente a expiré  <br/> |
|Nombre d’interrogations actuellement actives  <br/> |Nombre d’interrogations actuellement actives (longues connexions au serveur)  <br/> |
|Nombre de sessions actuellement actives  <br/> |Nombre actuel de points de terminaison enregistrés dans le service de mobilité  <br/> |
|Nombre de sessions actuellement actives avec abonnements de présence actifs  <br/> |Nombre de sessions actuellement actives avec abonnements de présence actifs  <br/> |
|Demandes de notifications push ayant échoué/seconde  <br/> |Taux de notifications push ayant échoué par seconde  <br/> |
|Demandes de notifications push réussies/seconde  <br/> |Taux de notifications push ayant réussi par seconde  <br/> |
|Demandes de notifications push limitées/seconde  <br/> |Taux de notifications push ayant été limitées par seconde  <br/> |
|Demandes de notifications push/seconde  <br/> |Taux de notifications push envoyées par seconde  <br/> |
|Demandes ayant échoué/seconde  <br/> |Taux de demandes ayant échoué par seconde  <br/> |
|Demandes reçues/seconde  <br/> |Taux de demandes reçues par seconde  <br/> |
|Demandes rejetées/seconde  <br/> |Taux de demandes rejetées par seconde  <br/> |
|Demandes réussies/seconde  <br/> |Taux de demandes réussies par seconde  <br/> |
|Demandes de lancement de session réussies/seconde  <br/> |Taux de demandes Get Location réussies par seconde. Les demandes de lancement de session consomment le plus de puissance de traitement sur le serveur. La charge maximale prise en charge est de 12 par seconde. La capacité à soutenir ces charges dépend des autres charges imposées sur le serveur. Le lancement d’une session signifie généralement la connexion d’un utilisateur ayant été déconnecté depuis un laps de temps étendu.  <br/> |
|Nombre total d’appels vocaux entrants refusés  <br/> |Nombre total d’appels vocaux entrants ayant été refusés  <br/> |
|Nombre total d’appels vocaux entrants ayant échoué  <br/> |Nombre total d’appels vocaux entrants ayant échoué  <br/> |
|Nombre total d’appels vocaux sortants ayant échoué  <br/> |Nombre total d’appels vocaux sortants ayant échoué  <br/> |
|Nombre total de sessions terminées par l’utilisateur  <br/> |Nombre total de sessions auxquelles les utilisateurs ont mis fin  <br/> |
|Nombre total de demandes de notifications push  <br/> |Nombre total de demandes de notifications push  <br/> |
|Nombre total de demandes de notifications push ayant échoué  <br/> |Nombre total de demandes de notifications push ayant échoué  <br/> |
|Nombre total de demandes de notifications push réussies  <br/> |Nombre total de demandes de notifications push ayant réussi  <br/> |
|Nombre total de demandes de notifications push limitées  <br/> |Nombre total de demandes de notifications push ayant limitées  <br/> |
|Nombre total de demandes ayant échoué  <br/> |Nombre total de demandes ayant échoué  <br/> |
|Nombre total de demandes reçues sur le canal de commande  <br/> |Nombre total de demandes reçues sur le canal de commande  <br/> |
|Nombre total de demandes rejetées  <br/> |Nombre total de demandes ayant été rejetées  <br/> |
|Nombre total de demandes réussies  <br/> |Nombre total de demandes effectuées au service de mobilité et ayant réussi  <br/> |
|Total de sessions initiées  <br/> |Nombre total de sessions qui ont été initiées depuis le démarrage du service de mobilité  <br/> |
|Total des sessions terminées pour inactivité utilisateur  <br/> |Nombre total de sessions terminées en raison d’un délai d’expiration d’inactivité  <br/> |
|Nombre total d’appels vocaux entrants réussis  <br/> |Nombre total d’appels vocaux entrants ayant été réussis  <br/> |
|Nombre total d’appels vocaux sortants réussis  <br/> |Nombre total d’appels vocaux sortants ayant été réussis  <br/> |
   
> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
