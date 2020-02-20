---
title: 'Lync Server 2013 : création d’enregistrements DNS pour le service de découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe908ac48bb71beea731c742665a979d9f96182f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Création d’enregistrements DNS pour le service de découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-20_

Vos utilisateurs de Lync mobile auront besoin d’activer la découverte automatique, qui implique la création de certains enregistrements DNS (Domain Name System). En fonction de vos besoins, vous avez besoin des éléments suivants :

  - Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent à partir du réseau de votre organisation.

  - Un enregistrement DNS externe ou public pour prendre en charge les utilisateurs mobiles qui se connectent à partir d’Internet

Pourquoi ? Vous devez créer un enregistrement DNS interne et un enregistrement DNS externe pour chaque domaine SIP.

Les enregistrements DNS que vous créez peuvent être des enregistrements A (hôte) ou CNAMe. Pour vous aider, consultez la rubrique relative à la création de ces enregistrements DNS internes et externes ci-dessous. Si vous devez effectuer des lectures supplémentaires sur les exigences DNS pour les utilisateurs mobiles, vous pouvez consulter la [configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Création d’un enregistrement CNAMe DNS interne

1.  Pour créer un enregistrement DNS interne, vous devez vous connecter à un serveur DNS de votre réseau à l’aide d’un compte de domaine membre du groupe administrateurs du domaine ou du groupe DnsAdmins.

2.  Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Dans l’arborescence de la console du serveur DNS, développez **zones de recherche directes** pour le domaine Active Directory dans lequel votre pool de directeurs et votre pool frontal Lync Server 2013 sont installés. (par exemple, contoso. local).

4.  Vérifier s’il existe un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool de directeurs pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet (FQDN) des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local). Si ce n’est pas le cas, il est possible que vous n’utilisiez pas un pool directeur et que vous devez utiliser le nom de domaine complet (FQDN) de votre pool frontal ou même un nom de domaine complet (FQDN) de serveur unique, si c’est votre configuration.

5.  En gardant cela à l’esprit, vérifiez si un enregistrement A (AAAA pour IPv6) hôte existe pour votre pool frontal pour un enregistrement DNS interne, il doit exister un enregistrement A (ou AAAA) hôte pour le nom de domaine complet des services Web internes pour votre pool frontal (par exemple , lyncwebpool01. contoso. local). Si ce n’est pas le cas, vous devez noter le nom de domaine complet (FQDN) du serveur frontal ou du serveur Standard Edition.

6.  Une fois que vous connaissez les enregistrements A (ou AAAA) de l’hôte, dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).

7.  Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel alias (CNAME)**.

8.  Dans **nom**de l’alias, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.

9.  Dans **nom de domaine complet (FQDN) pour l’hôte de destination**, tapez ou naviguez jusqu’au nom de domaine complet des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local), puis cliquez sur **OK**.

10. Vous devez créer un enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Création d’un enregistrement CNAMe DNS externe

1.  Pour créer un enregistrement CNAMe DNS externe, vous devez vous connecter à votre fournisseur DNS public, puis suivre nos étapes. Nous ne pouvons pas décrire exactement où vous allez dans l’environnement de votre fournisseur DNS car il peut y avoir différentes façons de gérer votre DNS externe, mais nous espérons que ces étapes seront utiles.

2.  Connectez-vous à votre fournisseur DNS externe à l’aide d’un compte qui peut créer des enregistrements DNS dans cet environnement.

3.  Un domaine SIP doit déjà être créé pour cet environnement. Développez la **zone de recherche directe** pour ce domaine SIP, ou sélectionnez-la en fonction de l’interface DNS externe utilisée.

4.  Vous devriez déjà voir un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool directeur (par exemple, lyncwebexdir01.contoso.com), vous devez donc confirmer qu’il s’agit bien. Si ce n’est pas le cas, il se peut que vous n’utilisiez pas de pool directeur. Si c’est le cas, vous devez utiliser le nom de domaine complet (FQDN) de votre pool frontal ou, si vous effectuez cette opération pour un seul serveur, pour votre serveur frontal ou votre serveur Standard Edition.

5.  Vous devrez également vérifier qu’il existe un enregistrement A (AAAA pour IPv6) hôte pour votre nom de domaine complet (FQDN) des services Web externes pour votre pool frontal (tel que lyncwebextpool01.contoso.com) ou un nom de domaine complet pour votre nom de domaine complet (FQDN) de serveur unique si vous n’avez pas de pool frontal. Comme indiqué à l’étape précédente, vous en aurez besoin ci-dessous si vous n’avez pas de pool directeur.

6.  À présent, dans le format approprié pour votre fournisseur DNS externe, sélectionnez l’option permettant de créer un **Nouvel alias (CNAME)** (il peut s’agir d’une option de menu ou d’un lien, selon le format du fournisseur DNS).

7.  Il doit y avoir une forme de zone de texte **nom d’alias** comme avec le DNS interne, vous devez entrer lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.

8.  Il doit également exister une forme de zone de texte **nom de domaine complet (FQDN) pour l’hôte cible** , où vous devez entrer le nom de domaine complet des services Web externes pour votre pool directeur (par exemple, lyncwebexdir01.contoso.com), puis cliquer sur OK ou exécuter toute action dans le DNS externe pour accepter la création de cette entrée. Comme indiqué à l’étape 4 ci-dessus, si vous n’avez pas de pool Directeur, vous devez utiliser le nom de domaine complet du pool frontal ou le nom de domaine complet du serveur unique que vous avez configuré, selon le cas.

9.  Vous devrez créer un nouvel enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync 2013.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Création d’un enregistrement DNS A interne

1.  Pour créer un enregistrement DNS interne, ouvrez une session sur un serveur DNS de votre réseau à l’aide d’un compte de domaine membre du groupe administrateurs du domaine ou du groupe DnsAdmins.

2.  Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **zones de recherche directes** pour votre domaine Active Directory (par exemple, contoso. local) où le pool de directeurs et les pools frontaux Lync Server 2013 sont installés.

4.  Vérifier s’il existe un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool de directeurs pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet (FQDN) des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local). Si ce n’est pas le cas, il se peut que vous n’utilisiez pas de pool directeur et que vous deviez utiliser l’adresse IP de votre pool frontal ou même une adresse IP de serveur unique, si c’est votre configuration.

5.  En gardant cela à l’esprit, vérifiez si un enregistrement A (AAAA pour IPv6) hôte existe pour votre pool frontal pour un enregistrement DNS interne, il doit exister un enregistrement A (ou AAAA) hôte pour le nom de domaine complet des services Web internes pour votre pool frontal (par exemple , lyncwebpool01. contoso. local). Si ce n’est pas le cas, vous devez prendre note de l’adresse IP pour le serveur frontal ou le serveur Standard Edition.

6.  Une fois que vous connaissez les enregistrements A (ou AAAA) de l’hôte, dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).

7.  Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel hôte (A ou AAAA)**.

8.  Dans **nom**, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.

9.  Dans **adresse IP**, tapez l’adresse IP interne des services Web du directeur (ou, si vous utilisez un programme d’équilibrage de la charge, tapez l’adresse IP virtuelle de l’équilibreur de charge du directeur). Comme indiqué à l’étape 4 ci-dessus, si vous n’utilisez pas de directeur, vous devrez peut-être entrer l’adresse IP du serveur frontal ou du serveur Standard Edition ou, si vous utilisez un programme d’équilibrage de la charge, tapez l’adresse IP du programme d’équilibrage de la charge du pool frontal.

10. Cliquez sur **Ajouter un hôte**, puis sur **OK**.

11. Pour créer un enregistrement A ou AAAA supplémentaire, répétez les étapes 8 à 10, en gardant à l’esprit que vous devrez créer des enregistrements de découverte automatique A ou AAAA dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync Server 2013.

12. Lorsque vous avez terminé de créer des enregistrements A (AAAA pour IPv6), cliquez sur **Terminé**.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Création d’un enregistrement DNS A externe

1.  Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public, puis suivez les étapes ci-après. Nous ne pouvons pas décrire exactement où vous allez dans l’environnement de votre fournisseur DNS car il peut y avoir différentes façons de gérer votre DNS externe, mais nous espérons que ces étapes seront utiles.

2.  Vous devez être connecté en tant que compte pouvant créer des enregistrements DNS dans cet environnement.

3.  Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com). Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).

4.  Vous devriez déjà voir un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool directeur (tel que lyncwebexdir01.contoso.com), vérifiez qu’il s’agit du point de vue et de l’adresse IP. Si ce n’est pas le cas, il se peut que vous n’utilisiez pas de pool directeur. Si c’est le cas, vous devez utiliser l’adresse IP de votre pool frontal, ou si vous effectuez cette opération pour un serveur unique, pour votre serveur frontal ou votre serveur Standard Edition. Gardez à l’esprit que vos serveurs peuvent également être derrière un équilibrage de charge ou utiliser un proxy inverse. Prenez note des adresses IP pour suivre les étapes ci-dessous.

5.  Vous devrez également vérifier qu’il existe un enregistrement A (AAAA pour IPv6) hôte pour votre nom de domaine complet (FQDN) des services Web externes pour votre pool frontal (tel que lyncwebextpool01.contoso.com) ou une adresse IP pour votre installation Lync à serveur unique si vous Aucun pool frontal. Comme indiqué à l’étape précédente, vous en aurez besoin ci-dessous si vous n’avez pas de pool directeur.

6.  À présent, dans le format approprié pour votre fournisseur DNS externe, sélectionnez l’option permettant de créer un **nouvel hôte a ou AAAA** (il peut s’agir d’une option de menu ou d’un lien, selon le format du fournisseur DNS).

7.  Vous devez entrer un **nom**, tapez lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.

8.  Il doit également exister une zone de texte **adresse IP** , où vous devez entrer l’adresse IP de votre pool de directeurs (par exemple, lyncwebexdir01.contoso.com) ou éventuellement l’adresse IP de l’équilibreur de charge de votre pool (ou une adresse IP de proxy inverse qui conduit au même), puis cliquer sur OK ou prendre l’une des mesures dans le DNS externe pour accepter la création de cette entrée. Comme indiqué à l’étape 4 ci-dessus, si vous n’avez pas de pool Directeur, vous devrez utiliser l’adresse IP du pool frontal ou l’adresse IP à serveur unique que vous avez configurée, selon le cas.

9.  Vous devrez créer un nouvel enregistrement Autodiscover A ou AAAA dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

