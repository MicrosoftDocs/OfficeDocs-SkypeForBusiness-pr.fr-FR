---
title: 'Lync Server 2013 : Prise en charge des infrastructures DNS'
TOCTitle: Prise en charge des infrastructures DNS (Domain Name System)
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425850(v=OCS.15)
ms:contentKeyID: 49296869
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge des infrastructures DNS dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-08_

Lync Server 2013 utilise le système DNS (Domain Name System) pour les opérations suivantes :

  - pour détecter les serveurs ou pools internes pour les communications de serveur à serveur ;

  - permettre aux clients de détecter le pool de serveurs frontaux ou le serveur Standard Edition utilisé pour diverses transactions SIP ;

  - associer les URL simples des conférences aux serveurs hébergeant ces conférences ;

  - permettre aux serveurs et clients externes de se connecter aux serveurs Edge ou au proxy inverse HTTP afin d’utiliser les fonctions de messagerie instantanée et de conférence ;

  - permettre aux périphériques de communications unifiées qui ne sont pas connectés de détecter le pool de serveurs frontaux ou le serveur Standard Edition exécutant le service web de mise à jour de périphériques, d’obtenir des mises à jour et d’envoyer des journaux ;

  - permettre aux clients mobiles de découvrir automatiquement les ressources de services web sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres des périphériques.

  - procéder à l’équilibrage de la charge DNS.

> [!NOTE]  
> Lync Server 2013 ne prend pas en charge les noms de domaine internationaux (IDN).

> [!IMPORTANT]  
> Le nom spécifié doit être identique au nom de l’ordinateur configuré sur le serveur. Par défaut, le nom d’un ordinateur qui n’est pas lié à un domaine est un nom court, pas un nom de domaine complet (FQDN). Générateur de topologie utilise des FQDN, pas des noms courts. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine. <strong>Utilisez uniquement les caractères standard</strong> (tels que A–Z, a–z, 0–9, et les traits d’union) quand vous assignez les FQDN de vos serveurs Lync, serveurs de périphérie et pools. N’utilisez pas les caractères ou traits de soulignement Unicode. Souvent, les caractères non standard dans un FQDN ne sont pas pris en charge par le DNS externe et les autorités de certification publique (quand le FQDN doit être assigné au SN dans le certificat).
