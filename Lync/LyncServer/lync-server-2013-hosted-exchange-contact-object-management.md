---
title: 'Lync Server 2013 : Gestion des objets Contact Exchange hébergés'
TOCTitle: Gestion des objets Contact Exchange hébergés
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412978(v=OCS.15)
ms:contentKeyID: 49299251
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des objets Contact Exchange hébergés dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-25_

Vous devez configurer un objet Contact pour chaque numéro de standard automatique et numéro d’accès d’abonné dans votre déploiement intersite.

Pour l’intégration à la messagerie unifiée Exchange hébergée, ocsumutil.exe ne peut pas être utilisé pour gérer des objets Contact car il dépend des paramètres de messagerie unifiée Exchange Active Directory Dans un déploiement intersite, Lync Server 2013 et la messagerie unifiée Exchange sont installés dans des forêts distinctes sans approbation entre elles. Pour des questions de sécurité, les administrateurs Lync Server 2013 n’ont pas directement accès aux paramètres Active Directory de messagerie unifiée Exchange. Lync Server 2013 fournit de ce fait un modèle différent pour la gestion des objets Contact dans un *espace d’adresse SIP partagé* accessible à Lync Server 2013 et au service de messagerie unifiée Exchange hébergée.

## Workflow d’objet Contact hébergé

Voici la procédure générale pour travailler avec votre administrateur de client Exchange hébergé en vue de gérer des objets contact :

1.  L’administrateur Exchange demande des numéros de téléphone pour l’accès abonné de messagerie unifiée Exchange et les objets Contact de standard automatique.

2.  L’administrateur Lync Server 2013 crée un objet Contact pour chaque numéro de téléphone et attribue une stratégie de messagerie vocale hébergée à chaque objet Contact.

3.  L’administrateur Lync Server 2013 fournit ces numéros de téléphone à l’administrateur Exchange.

4.  Ce dernier attribue les numéros de téléphone aux plans de numérotation de messagerie unifiée Exchange appropriés pour les standards automatiques et l’accès abonné.

> [!NOTE]  
> Il n’est pas nécessaire de configurer des paramètres de plan de numérotation Lync Server 2013 sur les objets Contact comme c’est le cas avec des déploiements sur site.

## Configuration d’objet Contact hébergés

> [!NOTE]  
> Avant que les objets Contact Lync Server 2013 puissent être activés pour la messagerie unifiée Exchange hébergée, une stratégie de messagerie vocale hébergée qui s’applique à eux doit être déployée. Cette stratégie peut avoir une portée globale, au niveau du site ou par utilisateur, dès lors qu’elle s’applique à l’objet Contact que vous voulez activer. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-hosted-voice-mail-policies.md">Stratégies de messagerie vocale hébergées dans Lync Server 2013</a> (contenu éventuellement en anglais).

Pour configurer des objets Contact de standard automatique et d’accès abonné hébergés dans un déploiement intersite, vous devez utiliser les applets de commande suivantes :

  - **New-CsExUmContact** crée un nouvel objet Contact pour la messagerie unifiée hébergée.

  - **Set-CsExUmContact** modifie un objet Contact existant pour la messagerie unifiée Exchange hébergée.

L’exemple qui suit crée un objet Contact de standard automatique :

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

Cet exemple crée un nouvel objet Contact de messagerie unifiée Exchange avec l’adresse SIP sip:exumaa1@fabrikam.com. Le nom du pool dans lequel s’exécute le service de serveur d’inscriptions Lync Server 2013 est RedmondPool.litwareinc.com. L’unité d’organisation Active Directory dans laquelle ces informations seront stockées est OU=ExUmContacts,DC=litwareinc,DC=com. Le numéro de téléphone de l’objet Contact est 2065554567. Le paramètre facultatif -AutoAttendant $True indique que cet objet est un objet Contact de standard automatique. Définir le paramètre -AutoAttendant sur False (la valeur par défaut) spécifie un objet Contact d’accès abonné.

Pour plus d’informations sur les applets de commande New-CsExUmContact et Set-CsExUmContact, reportez-vous à la documentation Lync Server Management Shell.

