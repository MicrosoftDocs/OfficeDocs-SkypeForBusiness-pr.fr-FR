---
title: "Lync Server 2013 : Déf. de l’exp. Ut. pour l’acq. manuelle d’un emplacement"
TOCTitle: Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398912(v=OCS.15)
ms:contentKeyID: 49298932
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-03_

Si un client se trouve à l’extérieur du réseau ou dans un sous-réseau non défini, l’utilisateur peut entrer manuellement un emplacement. Mais pendant un appel d’urgence, l’appel sera tout d’abord acheminé vers un répartiteur de centre de réponse aux appels d’urgence (Emergency Call Response Center, ou ECRC) E9-1-1 national ou régional avant d’être acheminé vers un centre téléphonique de sécurité publique (Public Safety Answering Point, ou PSAP). L’ECRC demande verbalement un emplacement à l’appelant, puis transfère l’appel au PSAP approprié en fonction des informations renseignées.

  - **Les utilisateurs doivent-ils être invités à entrer un emplacement lorsque le service d’informations sur l’emplacement n’en fournit pas un automatiquement ?**  
    Par exemple, si un client se trouve dans un sous-réseau non défini, au domicile de l’utilisateur, dans un hôtel ou ailleurs à l’extérieur du réseau, l’utilisateur doit-il entrer un emplacement ?
    
    Vous pouvez configurer le paramètre **Emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client. Si vous lui attribuez la valeur Non, l’utilisateur ne sera pas invité à entrer un emplacement. Si vous lui attribuez la valeur Oui, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite. Si vous lui attribuez la valeur Clause d’exclusion de responsabilité, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera s’il essaie d’ignorer le message d’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.

Quand un utilisateur entre manuellement un emplacement, ce dernier est mappé à l’adresse MAC de la passerelle par défaut du réseau du client. Il est ensuite stocké dans une table d’utilisateurs individuels située sur le client. Quand l’utilisateur retourne à un emplacement déjà enregistré, le client Lync est automatiquement défini sur cet emplacement.

> [!NOTE]  
> Vous pouvez uniquement modifier l’emplacement actuel de votre client, mais vous pouvez supprimer les emplacements stockés dans la table des utilisateurs locaux.
