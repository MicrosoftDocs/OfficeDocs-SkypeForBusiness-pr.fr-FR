---
title: Événements UCWA dans Skype entreprise Server
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
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Résumé : en savoir plus sur l’API Web de communications unifiées (UCWA) dans Skype entreprise Server.'
ms.openlocfilehash: db6aee15564fe9fca05c33ec5a6dd37988195956
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817623"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Événements UCWA dans Skype entreprise Server
 
**Résumé :** En savoir plus sur l’API Unified Communications Web API (UCWA) dans Skype entreprise Server.
  
Skype entreprise Server utilise l’API Unified Communications Web API (UCWA) à diverses fins, d’un point de vue de l’accès à Microsoft Exchange pour les recherches de contacts pour la mise à jour de la présence pour les clients mobiles.
  
L’API UCWA écrit les enregistrements liés aux opérations en tant qu’événements de type information, avertissement ou erreur. Le tableau suivant décrit les événements pouvant être écrits par les composants de l’API UCWA.
  
|**ID d’événement**|**Type d’événement**|**Résumé**|**Cause et solution**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Information  <br/> |API UCWA initialisée  <br/> |N/D  <br/> N/D  <br/> |
|20002  <br/> |Erreur  <br/> |L’API UCWA a rencontré une exception inattendue pendant son initialisation.  <br/> |Une erreur inattendue s’est produite pendant l’initialisation.  <br/> Examinez les détails de l’exception dans l’entrée correspondante du journal des événements pour déterminer la cause possible.  <br/> |
|20003  <br/> |Erreur  <br/> |L’API UCWA a rencontré une exception non traitée.  <br/> |Une exception non traitée s’est produite.  <br/> Redémarrez le serveur. Si le problème persiste, contactez le support technique.  <br/> |
|20004  <br/> |Erreur  <br/> |Impossible d’accéder à Exchange pour la photo HD  <br/> |La connexion à Exchange n’est pas disponible.  <br/> Vérifiez que la connexion à Exchange est disponible.  <br/> |
|20005  <br/> |Information  <br/> |Récupération de l’échec de l’accès à Exchange pour la photo HD  <br/> |N/A  <br/> |
|20006  <br/> |Erreur  <br/> |Impossible d’accéder à Exchange pour la recherche de contact  <br/> |La connexion à Exchange n’est pas disponible.  <br/> Vérifiez que la connexion à Exchange est disponible.  <br/> |
|20007  <br/> |Information  <br/> |Récupération de l’échec de la recherche de contact dans Exchange  <br/> |N/A  <br/> |
|20008  <br/> |Avertissement  <br/> |Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par application  <br/> |Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par application  <br/> Vérifiez si les clients possèdent des abonnements superflus.  <br/> |
|20009  <br/> |Avertissement  <br/> |Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par lot  <br/> |Tentative de souscription à un nombre d’abonnements aux informations de présence supérieur au nombre autorisé par lot  <br/> Vérifiez si les clients possèdent des abonnements superflus.  <br/> |
|20010  <br/> |Erreur  <br/> |Impossible de récupérer les données de la bande entrante  <br/> |Impossible de récupérer les données de la bande entrante  <br/> Si le problème persiste, contactez le support technique.  <br/> |
|20011  <br/> |Erreur  <br/> |Impossible de s’abonner aux informations de présence  <br/> |Impossible de s’abonner aux informations de présence  <br/> Si le problème persiste, contactez le support technique.  <br/> |
|20012  <br/> |Erreur  <br/> |Échec de l’enregistrement du point de terminaison  <br/> |Échec de l’enregistrement du point de terminaison  <br/> Si le problème persiste, contactez le support technique.  <br/> |
|20013  <br/> |Erreur  <br/> |Le MCU de messagerie instantanée n’est pas disponible.  <br/> |Le MCU de messagerie instantanée n’est pas disponible.  <br/> Vérifiez si le MCU de messagerie instantanée est en cours d’exécution.  <br/> |
|20014  <br/> |Information  <br/> |Récupération de l’échec de la connexion au MCU de messagerie instantanée  <br/> |N/A  <br/> |
|20015  <br/> |Erreur  <br/> |Le MCU AV n’est pas disponible.  <br/> |Le MCU AV n’est pas disponible.  <br/> Vérifiez si le MCU AV est en cours d’exécution.  <br/> |
|20016  <br/> |Information  <br/> |Récupération de l’échec de la connexion au MCU AV  <br/> |N/A  <br/> |
|20017  <br/> |Erreur  <br/> |Le MCU AS n’est pas disponible.  <br/> |Le MCU AS n’est pas disponible.  <br/> Vérifiez si le MCU AS est en cours d’exécution.  <br/> |
|20018  <br/> |Information  <br/> |Récupération de l’échec de la connexion au MCU AS  <br/> |N/A  <br/> |
|20019  <br/> |Erreur  <br/> |Le MCU de données n’est pas disponible.  <br/> |Le MCU de données n’est pas disponible.  <br/> Vérifiez si le MCU de données est en cours d’exécution.  <br/> |
|20020  <br/> |Information  <br/> |Récupération de l’échec de la connexion au MCU de données  <br/> |N/A  <br/> |
|20021  <br/> |Erreur  <br/> |Impossible de rejoindre le MCU de messagerie instantanée  <br/> |Impossible de rejoindre le MCU de messagerie instantanée  <br/> Vérifiez si le MCU de messagerie instantanée est en cours d’exécution.  <br/> |
|20022  <br/> |Erreur  <br/> |Impossible de rejoindre le MCU AV  <br/> |Impossible de rejoindre le MCU AV  <br/> Vérifiez si le MCU AV est en cours d’exécution.  <br/> |
|20023  <br/> |Erreur  <br/> |Impossible de rejoindre le MCU AS  <br/> |Impossible de rejoindre le MCU AS  <br/> Vérifiez si le MCU AS est en cours d’exécution.  <br/> |
|20024  <br/> |Erreur  <br/> |Impossible de rejoindre le MCU de données  <br/> |Impossible de rejoindre le MCU de données  <br/> Vérifiez si le MCU de données est en cours d’exécution.  <br/> |
|20025  <br/> |Erreur  <br/> |Impossible d’accéder à Active Directory pour la photo  <br/> |La connexion à Active Directory n’est pas disponible.  <br/> Vérifiez que la connexion à Active Directory est disponible.  <br/> |
|20026  <br/> |Information  <br/> |Récupération de l’échec de l’accès à Active Directory pour la photo  <br/> |N/A  <br/> |
|20027  <br/> |Avertissement  <br/> |Impossible d’effectuer la désérialisation  <br/> |Impossible d’effectuer la désérialisation  <br/> Si le problème persiste, contactez le support technique.  <br/> |
   

