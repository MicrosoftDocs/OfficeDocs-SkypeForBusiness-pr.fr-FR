---
title: 'Lync Server 2013 : Configuration de DNS pour la prise en charge de périphérie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c905c8fff7a67b26a7df8d2c741ce0a16fddce6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Configuration de DNS pour la prise en charge de périphérie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-15_

Vous devez configurer les enregistrements DNS (Domain Name System) pour les interfaces de périphérie interne et externe, y compris les interfaces de serveur Edge et de proxy inverse. Par défaut, les serveurs de périphérie ne sont pas joints à un domaine et ne disposent pas de nom de domaine complet (nom de domaine complet). Le serveur de périphérie est uniquement désigné par le nom court (ordinateur), et non par un nom de domaine complet. Toutefois, le générateur de topologie utilise les noms de domaine complets et non les noms courts. Le nom du serveur de périphérie doit correspondre au nom de domaine complet utilisé par le générateur de topologie. Pour ce faire, vous devez définir un suffixe DNS qui, lorsqu’il est combiné avec le nom de l’ordinateur, génère le FQDN attendu. Utilisez la procédure suivante dans « pour ajouter le suffixe DNS au nom de l’ordinateur sur un serveur Edge qui n’est pas joint à un domaine » pour ajouter le suffixe DNS au nom de l’ordinateur.

<div>


> [!NOTE]  
> Par défaut, DNS utilise un algorithme de tourniquet pour faire pivoter l’ordre des données d’enregistrement de ressource renvoyées dans les réponses de la requête lorsque plusieurs enregistrements de ressource du même type existent pour un nom de domaine DNS interrogé. L’équilibrage de charge DNS de Lync Server 2013 dépend du mécanisme de tourniquet DNS en tant que composant du mécanisme d’équilibrage de charge DNS. Vérifiez que le paramètre de tourniquet n’a pas été désactivé. Si vous utilisez un serveur DNS qui n’exécute pas de système d’exploitation Windows, vérifiez que la commande d’enregistrement de ressource à répétition alternée est activée.



</div>

Pour créer et vérifier chaque enregistrement SRV DNS, procédez comme suit dans «**pour créer un enregistrement SRV DNS**». Utilisez la procédure de la section «**pour créer un enregistrement DNS a**» pour définir les enregistrements DNS a requis pour l’accès des utilisateurs externes. Pour vérifier que les enregistrements sont configurés et qu’ils fonctionnent correctement, voir la section «**pour vérifier un enregistrement DNS**» de cette rubrique. Pour plus d’informations sur les enregistrements nécessaires à la prise en charge de l’accès des utilisateurs externes, voir [déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>Pour ajouter le suffixe DNS au nom de l’ordinateur sur un serveur Edge qui n’est pas joint à un domaine

1.  Sur l’ordinateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **ordinateur**, puis cliquez sur **Propriétés**.

2.  Sous **paramètres de nom d’ordinateur, de domaine et de groupe de travail**, cliquez sur **modifier les paramètres**.

3.  Dans l’onglet nom de l' **ordinateur** , cliquez sur **modifier**.

4.  Dans la **modification du nom ou du domaine**de l’ordinateur, cliquez sur **plus**.

5.  Dans **nom d’ordinateur NetBIOS et suffixe DNS**, dans **suffixe DNS principal de cet ordinateur**, tapez le nom de votre domaine interne (par exemple, Corp.contoso.com), puis cliquez sur **OK** à trois reprises.

6.  Redémarrez l’ordinateur.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>Pour créer un enregistrement SRV DNS

1.  Sur le serveur DNS approprié, cliquez sur **Démarrer**, sur **panneau de configuration**, sur **Outils d’administration**, puis sur **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez configurer le DNS de manière à ce qu’il y ait : 1) entrées DNS externes pour les recherches DNS externes par les utilisateurs distants et les partenaires fédérés ; 2) entrées pour les recherches DNS pour une utilisation par les serveurs Edge au sein du réseau de périmètre (également connu sous le nom de DMZ, zone démilitarisée et sous-réseau filtré), y compris les enregistrements des serveurs internes exécutant Lync Server 2013 ; et 3) entrées DNS internes pour les recherches par les clients et serveurs internes exécutant Lync Server 2013.

    
    </div>

2.  Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, puis cliquez avec le bouton droit sur le domaine sur lequel Lync Server 2013 est installé.

3.  Cliquez sur **nouveaux enregistrements**.

4.  Dans **Sélectionner un type d’enregistrement de ressource**, tapez **emplacement du service (SRV)**, puis cliquez sur **créer un enregistrement**.

5.  Fournissez toutes les informations requises pour l’enregistrement SRV DNS.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>Pour créer un enregistrement DNS A

1.  Sur le serveur DNS, cliquez sur **Démarrer**, sur **panneau de configuration**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 est installé.

3.  Cliquez sur **nouvel hôte (A)**.

4.  Fournissez toutes les informations requises pour l’enregistrement SRV DNS.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>Pour vérifier un enregistrement DNS

1.  Connectez-vous à un ordinateur client dans le domaine.

2.  Cliquez sur **Démarrer **, puis sur **Exécuter **.

3.  À l’invite de commandes, exécutez la commande suivante :
    
        nslookup <FQDN edge interface>

4.  Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet (FQDN).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création d’un enregistrement SRV DNS pour l’intégrer à la messagerie unifiée Exchange hébergée](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

