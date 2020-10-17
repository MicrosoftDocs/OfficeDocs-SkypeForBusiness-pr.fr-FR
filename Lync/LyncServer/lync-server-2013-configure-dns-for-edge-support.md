---
title: 'Lync Server 2013 : configuration de DNS pour la prise en charge du serveur Edge'
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
ms.openlocfilehash: e9ccf25c2bbaf6c77c72d35f1fa5ac82fd67d011
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537151"
---
# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Configuration de DNS pour la prise en charge du serveur Edge dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-15_

Vous devez configurer des enregistrements DNS pour les interfaces Edge internes et externes, notamment pour les interfaces des serveurs Edge et proxy inverse. Par défaut, les serveurs Edge ne sont pas joints à un domaine et n’ont pas de nom de domaine complet. Il est fait référence au serveur Edge par un nom court (ordinateur) et non un nom de domaine complet. Toutefois, le générateur de topologies utilise des noms de domaine complets, pas des noms courts. Le nom du serveur Edge doit correspondre au nom de domaine complet utilisé par le générateur de topologie. Pour ce faire, vous définissez un suffixe DNS qui, quand il est associé au nom de l’ordinateur, correspond au nom de domaine complet attendu. Utilisez la procédure suivante de « Pour ajouter le suffixe DNS au nom d’ordinateur du serveur Edge qui n’est pas joint à un domaine » pour ajouter le suffixe DNS au nom de l’ordinateur.

<div>


> [!NOTE]  
> Par défaut, DNS utilise un algorithme de répétition alternée pour faire pivoter l’ordre des données des enregistrements de ressource renvoyées dans les réponses aux requêtes où existent plusieurs enregistrements de ressources du même type pour un nom de domaine DNS interrogé. L’équilibrage de charge DNS de Lync Server 2013, dépend de la répétition alternée DNS dans le cadre du mécanisme d’équilibrage de la charge DNS. Vérifiez que le paramètre Round-Robin n’a pas été désactivé. Si vous utilisez un serveur DNS qui n’exécute pas de système d’exploitation Windows, vérifiez que la commande d’enregistrement de ressource à répétition alternée est activée.



</div>

Utilisez les procédures suivantes de « **Pour créer un enregistrement DNS SRV** » pour créer et vérifier chaque enregistrement DNS SRV. Utilisez la procédure de « **Pour créer un enregistrement DNS A** » pour définir les enregistrements DNS A requis pour l’accès utilisateur externe. Pour confirmer que les enregistrements sont configurés et fonctionnent correctement, voir « **Pour vérifier un enregistrement DNS** » dans cette rubrique. Pour plus d’informations sur chaque enregistrement requis pour prendre en charge l’accès des utilisateurs externes, voir [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>Pour ajouter le suffixe DNS au nom de l’ordinateur sur un serveur Edge qui n’est pas joint à un domaine

1.  Sur l’ordinateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Ordinateur**, puis cliquez sur **Propriétés**.

2.  Sous **Paramètres de nom d’ordinateur, de domaine et de groupe de travail**, cliquez sur **Modifier les paramètres**.

3.  Sous l’onglet **Nom de l’ordinateur**, cliquez sur **Modifier**.

4.  Dans **Modification du nom ou du domaine de l’ordinateur**, cliquez sur **Plus**.

5.  Dans **Nom d’ordinateur NetBIOS et suffixe DNS**, dans **Suffixe DNS principal de cet ordinateur**, tapez le nom de votre domaine interne (par exemple, corp.contoso.com), puis cliquez trois fois sur **OK**.

6.  Redémarrez l’ordinateur.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>Pour créer un enregistrement DNS SRV

1.  Sur le serveur DNS approprié, cliquez sur **Démarrer**, sur **Panneau de configuration**, sur **Outils d’administration**, puis sur **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous devez configurer DNS de sorte qu’il y ait : 1) entrées DNS externes pour les recherches DNS externes par les utilisateurs distants et les partenaires fédérés ; 2) entrées pour les recherches DNS utilisées par les serveurs Edge dans le réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré), y compris les enregistrements A pour les serveurs internes exécutant Lync Server 2013 ; et 3) entrées DNS internes pour les recherches par les clients et serveurs internes exécutant Lync Server 2013.

    
    </div>

2.  Dans l’arborescence de la console pour votre domaine SIP, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine où Lync Server 2013 est installé.

3.  Cliquez sur **Nouveaux enregistrements**.

4.  Dans **Choisissez un type d’enregistrement de ressource**, tapez **Emplacement du service (SRV)**, puis cliquez sur **Créer un enregistrement**.

5.  Fournissez toutes les informations requises pour l’enregistrement DNS SRV.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>Pour créer un enregistrement DNS A

1.  Sur le serveur DNS, cliquez sur **Démarrer**, sur **Panneau de configuration**, sur **Outils d’administration**, puis sur **DNS**.

2.  Dans l’arborescence de la console pour votre domaine SIP, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine dans lequel Lync Server 2013 est installé.

3.  Cliquez sur **Nouvel hôte (A)**.

4.  Fournissez toutes les informations requises pour l’enregistrement DNS SRV.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>Pour vérifier un enregistrement DNS

1.  Ouvrez une session sur un ordinateur client du domaine.

2.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

3.  À l’invite de commandes, exécutez la commande suivante :
    
        nslookup <FQDN edge interface>

4.  Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer un enregistrement SRV DNS pour l’intégration à la messagerie unifiée Exchange hébergée](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

