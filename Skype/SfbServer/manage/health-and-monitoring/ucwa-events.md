---
title: Événements UCWA dans Skype Entreprise Server
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
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Résumé : Découvrez l’API web de communications unifiées (UCWA) dans Skype Entreprise Server.'
ms.openlocfilehash: 32022d44635e9560e28723812c1247fda38cf00d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763622"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>Événements UCWA dans Skype Entreprise Server
 
**Résumé :** Découvrez l’API UCWA (Unified Communications Web API) dans Skype Entreprise Server.
  
Skype Entreprise Server utilise l’API web de communications unifiées (UCWA) à plusieurs fins, depuis l’accès à Microsoft Exchange pour les recherches de contacts jusqu’à la mise à jour de la présence pour les clients mobiles.
  
UCWA écrit des enregistrements de comportement opérationnel en tant qu’événements de types Informationnel, Avertissement et Erreur. Le tableau suivant décrit les événements qui peuvent être écrits par les composants UCWA.
  
|**ID d’évènement**|**Type d’événement**|**Summary**|**Cause et résolution**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informatif  <br/> |Initialisation d’UCWA  <br/> |N/A  <br/> N/A  <br/> |
|20002  <br/> |Erreur  <br/> |UCWA a rencontré une exception inattendue lors de l’initialisation  <br/> |Une erreur inattendue s’est produite lors de l’initialisation  <br/> Examiner les détails de l’exception dans l’entrée du journal des événements associée pour déterminer la cause possible  <br/> |
|20003  <br/> |Erreur  <br/> |UCWA a rencontré une exception non  <br/> |Une exception nonmenée s’est produite  <br/> Redémarrez le serveur. Si le problème persiste, contactez le support technique  <br/> |
|20004  <br/> |Erreur  <br/> |Impossible d’Exchange la photo HD  <br/> |La connexion à Exchange n’est pas disponible  <br/> Assurez-vous que la connexion à Exchange est disponible  <br/> |
|20005  <br/> |Informatif  <br/> |Récupération de l’échec de l’accès Exchange pour la photo HD  <br/> |N/A  <br/> |
|20006  <br/> |Erreur  <br/> |Impossible d’accéder Exchange pour la recherche de contact  <br/> |La connexion à Exchange n’est pas disponible  <br/> Assurez-vous que la connexion à Exchange est disponible  <br/> |
|20007  <br/> |Informatif  <br/> |Récupération de l’échec de la recherche de contact dans Exchange  <br/> |N/A  <br/> |
|20008  <br/> |Avertissement  <br/> |Tentative d’abonnement à un nombre d’abonnements de présence supérieur aux abonnements de présence autorisés par application  <br/> |Tentative d’abonnement à un nombre d’abonnements de présence supérieur aux abonnements de présence autorisés par application  <br/> Vérifier les clients pour les abonnements inutiles  <br/> |
|20009  <br/> |Avertissement  <br/> |Tentative d’abonnement à un nombre d’abonnements de présence supérieur aux abonnements de présence autorisés par lot  <br/> |Tentative d’abonnement à un nombre d’abonnements de présence supérieur aux abonnements de présence autorisés par lot  <br/> Vérifier les clients pour les abonnements inutiles  <br/> |
|20010  <br/> |Erreur  <br/> |Impossible de récupérer les données inbandes  <br/> |Impossible de récupérer les données inbandes  <br/> Si le problème persiste, contactez le support technique  <br/> |
|20011  <br/> |Erreur  <br/> |Impossible de s’abonner à la présence  <br/> |Impossible de s’abonner à la présence  <br/> Si le problème persiste, contactez le support technique  <br/> |
|20012  <br/> |Erreur  <br/> |Échec de l’inscription du point de terminaison  <br/> |Échec de l’inscription du point de terminaison  <br/> Si le problème persiste, contactez le support technique  <br/> |
|20013  <br/> |Erreur  <br/> |Le MCU de messagerie instantanée n’est pas disponible  <br/> |Le MCU de messagerie instantanée n’est pas disponible  <br/> Vérifier si le MCU de messagerie instantanée est en cours d’exécution  <br/> |
|20014  <br/> |Informatif  <br/> |Récupération de l’échec de la connexion au MCU de messagerie instantanée  <br/> |N/A  <br/> |
|20015  <br/> |Erreur  <br/> |Le MCU antivirus n’est pas disponible  <br/> |Le MCU antivirus n’est pas disponible  <br/> Vérifier si le MCU antivirus est en cours d’exécution  <br/> |
|20016  <br/> |Informatif  <br/> |Récupération de l’échec de la connexion au MCU antivirus  <br/> |N/A  <br/> |
|20017  <br/> |Erreur  <br/> |AS MCU n’est pas disponible  <br/> |AS MCU n’est pas disponible  <br/> Vérifier si le MCU AS est en cours d’exécution  <br/> |
|20018  <br/> |Informatif  <br/> |Récupération de l’échec de la connexion au MCU AS  <br/> |N/A  <br/> |
|20019  <br/> |Erreur  <br/> |Le MCU de données n’est pas disponible  <br/> |Le MCU de données n’est pas disponible  <br/> Vérifier si le MCU de données est en cours d’exécution  <br/> |
|20020  <br/> |Informatif  <br/> |Récupération de l’échec de la connexion au MCU de données  <br/> |N/A  <br/> |
|20021  <br/> |Erreur  <br/> |Impossible de rejoindre le MCU de messagerie instantanée  <br/> |Impossible de rejoindre le MCU de messagerie instantanée  <br/> Vérifier si le MCU de messagerie instantanée est en cours d’exécution  <br/> |
|20022  <br/> |Erreur  <br/> |Impossible de rejoindre le MCU av  <br/> |Impossible de rejoindre le MCU av  <br/> Vérifier si le MCU antivirus est en cours d’exécution  <br/> |
|20023  <br/> |Erreur  <br/> |Impossible de rejoindre le MCU AS  <br/> |Impossible de rejoindre le MCU AS  <br/> Vérifier si le MCU AS est en cours d’exécution  <br/> |
|20024  <br/> |Erreur  <br/> |Impossible de joindre le MCU de données  <br/> |Impossible de joindre le MCU de données  <br/> Vérifier si le MCU de données est en cours d’exécution  <br/> |
|20025  <br/> |Erreur  <br/> |Impossible d’accéder à Active Directory pour la photo  <br/> |La connexion à Active Directory n’est pas disponible  <br/> Assurez-vous que la connexion à Active Directory est disponible  <br/> |
|20026  <br/> |Informatif  <br/> |Récupération de l’échec de l’accès à Active Directory pour la photo  <br/> |N/A  <br/> |
|20027  <br/> |Avertissement  <br/> |Impossible de désérialiser  <br/> |Impossible de désérialiser  <br/> Si le problème persiste, contactez le support technique  <br/> |
   

