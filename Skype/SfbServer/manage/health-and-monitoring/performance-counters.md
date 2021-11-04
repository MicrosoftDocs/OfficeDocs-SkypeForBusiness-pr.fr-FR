---
title: Compteurs de performances de mobilité dans Skype Entreprise Server
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
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Résumé : Découvrez les compteurs de performances que vous pouvez utiliser pour surveiller les serveurs exécutant l’API UCWA (Unified Communications Web API) et le service Skype Entreprise Server Mcx Mobility Service.'
ms.openlocfilehash: 983caf353b5fb18a438a9ad2128ec24feec97742
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754733"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Compteurs de performances de mobilité dans Skype Entreprise Server
 
**Résumé :** Découvrez les compteurs de performances que vous pouvez utiliser pour surveiller les serveurs exécutant l’API UCWA (Unified Communications Web API) et le service Skype Entreprise Server Mcx Mobility Service.
  
Les tableaux suivants répliquent les noms et les descriptions des compteurs de performance que vous pouvez utiliser pour surveiller les serveurs exécutant l’API web de communications unifiées (UCWA) et le service Skype Entreprise Server Mcx Mobility Service. 
  
Le nom de catégorie pour les compteurs dans la table UCWA est **LS:WEB - UCWA**.
  
Le nom de catégorie des compteurs dans la table Service de mobilité Mcx est **LS:WEB - Mobile Communication Service**.

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
## <a name="performance-counters-for-ucwa"></a>Compteurs de performances pour UCWA

|Compteur|Description|
|:-----|:-----|
|Nombre d’applications actives  <br/> |Nombre actuel d’applications  <br/> |
|Active Application Sharing Modality Count  <br/> |Nombre actuel de modalités de partage d’application  <br/> |
|Active Audio Modality Count  <br/> |Nombre actuel de modalités audio  <br/> |
|Active Data Collaboration Modality Count  <br/> |Nombre actuel de modalités de collaboration de données  <br/> |
|Latence d’obtenir une photo Active Directory (ms)  <br/> |Ce compteur indique le temps moyen (en millisecondes) pour récupérer une photo à partir d’Active Directory  <br/> |
|Active Messaging Modality Count  <br/> |Nombre actuel de modalités de messagerie  <br/> |
|Active Panoramic Video Modality Count  <br/> |Nombre actuel de modalités de vidéo panoramique  <br/> |
|Active Pending Get Count  <br/> |Le nombre d’attentes actives obtient ; connexions de longue durée au serveur ;  <br/> |
|Nombre de sessions actives  <br/> |Nombre actuel de points de terminaison enregistrés dans UCWA par application et total  <br/> |
|Nombre d’instances d’utilisateurs actifs  <br/> |Nombre actuel d’instances utilisateur  <br/> |
|Instances utilisateur actives sans application  <br/> |Nombre actuel d’instances utilisateur sans application  <br/> |
|Active Video Modality Count  <br/> |Nombre actuel de modalités vidéo  <br/> |
|Demandes de création d’applications reçues/seconde  <br/> |Taux de demandes de création d’applications reçues par seconde  <br/> |
|AS MCU Join Failures  <br/> |Nombre d’échecs de joint du MCU AS  <br/> |
|Échecs de joints du MCU av  <br/> |Nombre d’échecs de joint du MCU antivirus  <br/> |
|Durée moyenne de démarrage de l’application (ms)  <br/> |Durée moyenne de démarrage de l’application en millisecondes  <br/> |
|Durée de vie moyenne de la session (ms)  <br/> |Durée de vie moyenne d’une session en millisecondes  <br/> |
|Data MCU Join Failures  <br/> |Nombre d’échecs de joint du MCU de données  <br/> |
|Exchange Latence de recherche de contact (ms)  <br/> |Ce compteur indique la durée moyenne (en millisecondes) de la recherche de contact dans Exchange  <br/> |
|Exchange HD Photo Get Latency (ms)  <br/> |Ce compteur indique le temps moyen (en millisecondes) pour récupérer une photo à partir d Exchange  <br/> |
|HTTP 4xx Responses/Second  <br/> |Taux de réponses par seconde avec code HTTP 4xx  <br/> |
|HTTP 5xx Responses/Second  <br/> |Taux de réponses par seconde avec code HTTP 5xx  <br/> |
|Échecs de joints au MCU de messagerie instantanée  <br/> |Nombre d’échecs de joint du MCU de messagerie instantanée  <br/> |
|Nombre d’échecs d’obtenir des photos Active Directory  <br/> |Nombre total d’échecs de récupération de photos à partir d’Active Directory  <br/> |
|Nombre d’échecs de recherche de contacts  <br/> |Nombre total d’échecs de recherche de contacts dans Exchange  <br/> |
|Nombre d’échecs de désérialisation  <br/> |Nombre total d’échecs de désérialisation  <br/> |
|Nombre d’échecs d’obtenir une photo HD  <br/> |Nombre total d’échecs de récupération de photos HD à partir de Exchange  <br/> |
|Over The Maximum Subscriptions Per Application  <br/> |Nombre de demandes d’abonnement au-dessus du nombre maximal autorisé par application  <br/> |
|Au-dessus du nombre maximal d’abonnements par lot  <br/> |Nombre de demandes d’abonnement au-dessus du nombre maximal autorisé par lot  <br/> |
|Échecs d’abonnement de présence  <br/> |Nombre d’échecs d’abonnement à la présence  <br/> |
|Enregistrement des échecs de point de terminaison  <br/> |Nombre d’échecs d’inscription des points de terminaison  <br/> |
|Demandes reçues/seconde  <br/> |Taux de demandes reçues par seconde  <br/> |
|Demandes réussies/seconde  <br/> |Taux de demandes réussies par seconde (codes de réponse HTTP 2xx/3xx)  <br/> |
|Création de demandes d’application réussi/seconde  <br/> |Taux de demandes de création d’applications réussies par seconde  <br/> |
|Timed Out Pending Get Count  <br/> |Nombre d’attentes dont le délai d’attente a été long  <br/> |
|Nombre total de demandes de création d’applications reçues  <br/> |Nombre total de demandes de création d’applications reçues depuis le début du service  <br/> |
|Nombre total de réponses HTTP 4xx  <br/> |Nombre total de réponses HTTP 4xx  <br/> |
|Nombre total de réponses HTTP 5xx  <br/> |Nombre total de réponses HTTP 5xx  <br/> |
|Nombre total de demandes reçues sur le canal de commande  <br/> |Quantité totale de demandes reçues sur le canal de commande  <br/> |
|Quantité totale de demandes réussies  <br/> |Nombre total de demandes qui ont réussi  <br/> |
|Nombre total de sessions initiées  <br/> |Nombre total de sessions lancées depuis le début du service  <br/> |
|Nombre total de sessions terminées en raison du délai d’inactivité  <br/> |Quantité totale de sessions qui ont été terminées suite à l’expiration du délai d’inactivité utilisateur  <br/> |
|Nombre total d’applications limitées  <br/> |Nombre d’applications limitées  <br/> |
   
**Compteurs de performance pour le service de mobilité Mcx**

|**Compteur**|**Description**|
|:-----|:-----|
|Durée de vie moyenne d’une session en millisecondes  <br/> |Durée de vie moyenne d’une session en millisecondes  <br/> |
|Abonnements actuels aux notifications push  <br/> |Quantité actuelle d’abonnements aux notifications push. Ce nombre, en association avec le nombre de sessions actuellement actives, représente le sous-ensemble des sessions actuellement actives inscrites pour Windows mobile ou iPhone appareils mobiles.  <br/> |
|Nombre d’interrogations réseau expirées actuellement actives  <br/> |Nombre d’interrogations réseau sont le délai d’attente a expiré  <br/> |
|Nombre d’interrogations actuellement actives  <br/> |Nombre d’interrogations actuellement actives (longues connexions au serveur)  <br/> |
|Nombre de sessions actuellement actives  <br/> |Quantité actuelle de points de terminaison enregistrés dans le service de mobilité  <br/> |
|Nombre de sessions actuellement actives avec abonnements de présence actifs  <br/> |Nombre de sessions actuellement actives avec abonnements de présence actifs  <br/> |
|Demandes de notifications push échouées/seconde  <br/> |Taux de notifications push ayant échoué par seconde  <br/> |
|Demandes de notifications push réussies/seconde  <br/> |Taux de notifications push ayant réussi par seconde  <br/> |
|Demandes de notifications push limitées/seconde  <br/> |Taux de notifications push ayant été limitées par seconde  <br/> |
|Demandes de notifications push/seconde  <br/> |Taux de notifications push envoyées par seconde  <br/> |
|Demandes échouées/seconde  <br/> |Taux de demandes ayant échoué par seconde  <br/> |
|Demandes reçues/seconde  <br/> |Taux de demandes reçues par seconde  <br/> |
|Demandes rejetées/seconde  <br/> |Taux de demandes rejetées par seconde  <br/> |
|Demandes réussies/seconde  <br/> |Taux de demandes réussies par seconde  <br/> |
|Demandes de lancement de session réussies/seconde  <br/> |Taux de demandes Get Location réussies par seconde. Les demandes de lancement de session consomment le plus de puissance de traitement sur le serveur. La charge maximale prise en charge est de 12 par seconde. La capacité à soutenir ces charges dépend des autres charges imposées sur le serveur. Le lancement d’une session signifie généralement la connexion d’un utilisateur ayant été déconnecté depuis un laps de temps étendu.  <br/> |
|Quantité totale d’appels vocaux entrants refusés  <br/> |Quantité totale d’appels vocaux entrants ayant été refusés  <br/> |
|Quantité totale d’appels vocaux entrants échoués  <br/> |Quantité totale d’appels vocaux entrants ayant échoué  <br/> |
|Quantité totale d’appels vocaux sortants échoués  <br/> |Quantité totale d’appels vocaux sortants ayant échoué  <br/> |
|Quantité totale de sessions terminées par l’utilisateur  <br/> |Quantité totale de sessions auxquelles les utilisateurs ont mis fin  <br/> |
|Quantité totale de demandes de notifications push  <br/> |Quantité totale de demandes de notifications push  <br/> |
|Quantité totale de demandes de notifications push échouées  <br/> |Quantité totale de demandes de notifications push ayant échoué  <br/> |
|Quantité totale de demandes de notifications push réussies  <br/> |Quantité totale de demandes de notifications push ayant réussi  <br/> |
|Quantité totale de demandes de notifications push limitées  <br/> |Quantité totale de demandes de notifications push ayant limitées  <br/> |
|Quantité totale de demandes échouées  <br/> |Quantité totale de demandes ayant échoué  <br/> |
|Quantité totale de demandes reçues sur le canal de commande  <br/> |Quantité totale de demandes reçues sur le canal de commande  <br/> |
|Quantité totale de demandes rejetées  <br/> |Quantité totale de demandes ayant été rejetées  <br/> |
|Quantité totale de demandes réussies  <br/> |Quantité totale de demandes effectuées au service de mobilité et ayant réussi  <br/> |
|Total de sessions initiées  <br/> |Quantité totale de sessions qui ont été initiées depuis le démarrage du service de mobilité  <br/> |
|Total des sessions terminées pour inactivité utilisateur  <br/> |Quantité totale de sessions qui ont été terminées suite à l’expiration du délai d’inactivité utilisateur  <br/> |
|Quantité totale d’appels vocaux entrants réussis  <br/> |Quantité totale d’appels vocaux entrants ayant été réussis  <br/> |
|Quantité totale d’appels vocaux sortants réussis  <br/> |Quantité totale d’appels vocaux sortants ayant été réussis  <br/> |
   
> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
