---
title: 'Lync Server 2013 : Création d’enregistrements DNS pour le service de découverte automatique'
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
ms.openlocfilehash: d91c67620a87fdd91a1755592175e8cf2964d259
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Création d’enregistrements DNS pour le service de découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-20_

Vos utilisateurs mobiles Lync vous auront besoin d’activer la découverte automatique, et d’une partie de la création d’enregistrements DNS (Domain Name System). En fonction de vos besoins, vous devez disposer des éléments suivants :

  - Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent au sein du réseau de votre organisation.

  - Enregistrement DNS externe ou public permettant de prendre en charge les utilisateurs mobiles qui se connectent à partir d’Internet

Pourquoi ? Vous devez créer un enregistrement DNS interne et un enregistrement DNS externe pour chaque domaine SIP.

Les enregistrements DNS que vous créez peuvent être des enregistrements de type (hôte) ou CNAMe. Pour vous aider, nous allons découvrir comment créer ces enregistrements DNS internes et externes ci-dessous. Pour plus d’informations sur la configuration requise pour les utilisateurs mobiles, vous pouvez consulter les [exigences techniques en matière de mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Création d’un enregistrement CNAMe DNS interne

1.  Pour créer un enregistrement DNS interne, vous devez vous connecter à un serveur DNS dans votre réseau à l’aide d’un compte de domaine membre du groupe administrateurs de domaine ou membre du groupe DnsAdmins.

2.  Ouvrez le composant logiciel enfichable d’administration DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Dans l’arborescence de la console du serveur DNS, développez **zones de recherche directe** pour le domaine Active Directory sur lequel se trouve votre pool de directeurs et votre pool de serveurs Lync Server 2013. (par exemple, contoso. local).

4.  Pour savoir si un enregistrement hôte A (AAAA pour IPv6) existe pour votre pool de Directors pour un enregistrement DNS interne, un enregistrement A doit exister pour le nom de domaine complet (FQDN) des services Web internes pour votre pool de répertoires (par exemple, lyncwebdir01. contoso. local). Si ce n’est pas le cas, il est possible que vous n’utilisiez pas un pool de directeurs et que vous deviez utiliser le nom de domaine complet (FQDN) du pool frontal ou même du nom de domaine complet (FQDN) du serveur pour votre installation.

5.  Tout en gardant à l’esprit que vous devez vérifier qu’il existe un enregistrement A (AAAA pour IPv6) pour votre pool frontal pour un enregistrement DNS interne, un enregistrement d’hôte A (ou AAAA) doit exister pour le nom de domaine complet des services Web internes de votre liste frontale (par exemple, , lyncwebpool01. contoso. local). Si ce n’est pas le cas, vous devez noter le nom de domaine complet (FQDN) du serveur frontal ou du serveur Standard Edition.

6.  Lorsque vous savez quels sont les enregistrements d’hôte A (ou AAAA), dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).

7.  Cliquez avec le bouton droit sur le nom de domaine SIP, puis cliquez sur **Nouvel alias (CNAME)**.

8.  Dans **nom**de l’alias, tapez lyncdiscoverinternal comme nom d’hôte de l’URL du service de découverte automatique interne.

9.  Dans **nom de domaine complet (FQDN) de l’hôte cible**, tapez ou accédez au nom de domaine complet des services Web internes de votre pool de répertoires (par exemple, lyncwebdir01. contoso. local), puis cliquez sur **OK**.

10. Vous devez créer un enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Création d’un enregistrement CNAMe DNS externe

1.  Pour créer un enregistrement CNAMe DNS externe, vous devez vous connecter à votre fournisseur DNS public, puis suivre les étapes décrites dans cette procédure. Nous ne sommes pas en mesure de décrire exactement l’endroit où se trouvent les éléments de l’environnement de votre fournisseur DNS, car il existe peut-être différentes manières de gérer votre DNS externe, mais nous espérons pouvoir suivre ces étapes.

2.  Connectez-vous à votre fournisseur DNS externe à l’aide d’un compte qui peut créer des enregistrements DNS dans cet environnement.

3.  Un domaine SIP doit déjà être créé pour cet environnement. Développez la **zone de recherche directe** pour ce domaine SIP ou sélectionnez-la en fonction de l’interface DNS externe utilisée.

4.  Vous devez déjà voir l’enregistrement d’un hôte A (AAAA pour IPv6) pour votre pool de réalisateurs (par exemple, lyncwebexdir01.contoso.com), alors confirmez-le. Si ce n’est pas le cas, il est possible que vous n’utilisiez pas un pool de réalisateurs. Si tel est le cas, vous devez utiliser le nom de domaine complet (FQDN) du pool frontal, ou si vous effectuez cette opération pour un serveur unique pour votre serveur frontal ou Standard Edition Server.

5.  Vous devez également vérifier qu’un enregistrement hôte A (AAAA pour IPv6) existe pour votre nom de domaine complet (FQDN) de votre service Web externe (par exemple, lyncwebextpool01.contoso.com), ou un nom de domaine complet pour votre nom de domaine complet (FQDN) de votre serveur principal si vous n’avez pas de pool frontal. Comme indiqué à l’étape précédente, vous devez disposer de ce qui suit si vous n’avez pas de pool de directeurs.

6.  À présent, dans le format approprié pour votre fournisseur DNS externe, sélectionnez l’option de création d’un **alias (CNAME)** (il s’agit d’une option de menu ou d’un lien, en fonction du format du fournisseur DNS).

7.  Il doit exister une forme de zone de texte **nom d’alias** comme le DNS interne, vous devez entrer lyncdiscover comme nom d’hôte de l’URL du service de découverte automatique externe.

8.  Dans le cas d’un **nom de domaine complet (FQDN)** , vous devez également entrer le nom de domaine complet (FQDN) des services Web externes pour votre pool de directeurs (par exemple, lyncwebexdir01.contoso.com), puis cliquer sur OK ou exécuter une action quelconque du DNS externe pour accepter la création de cette entrée. Comme indiqué à l’étape 4, si vous n’avez pas de pool de directeurs, vous devez utiliser le nom de domaine complet du pool frontal ou le nom de domaine complet (FQDN) du serveur configuré, le cas échéant.

9.  Vous devez créer un nouvel enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync 2013.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Création d’un enregistrement DNS interne

1.  Pour créer un enregistrement DNS interne, connectez-vous à un serveur DNS dans votre réseau à l’aide d’un compte de domaine membre du groupe Domain Admins ou membre du groupe DnsAdmins.

2.  Ouvrez le composant logiciel enfichable d’administration DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.

3.  Dans le cas d’un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **zones de recherche directe** pour votre domaine Active Directory (par exemple, contoso. local) sur lequel est installé votre pool de directeurs et votre pool frontal Lync Server 2013.

4.  Pour savoir si un enregistrement hôte A (AAAA pour IPv6) existe pour votre pool de Directors pour un enregistrement DNS interne, un enregistrement A doit exister pour le nom de domaine complet (FQDN) des services Web internes pour votre pool de répertoires (par exemple, lyncwebdir01. contoso. local). Si ce n’est pas le cas, il est possible que vous n’utilisiez pas un pool de réalisateurs et que vous deviez utiliser l’adresse IP de votre pool frontal ou même une seule adresse IP de serveur, si c’est votre configuration.

5.  Tout en gardant à l’esprit que vous devez vérifier qu’il existe un enregistrement A (AAAA pour IPv6) pour votre pool frontal pour un enregistrement DNS interne, un enregistrement d’hôte A (ou AAAA) doit exister pour le nom de domaine complet des services Web internes de votre liste frontale (par exemple, , lyncwebpool01. contoso. local). Si ce n’est pas le cas, vous devez noter l’adresse IP du serveur frontal ou du serveur Standard Edition Server.

6.  Lorsque vous savez quels sont les enregistrements d’hôte A (ou AAAA), dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).

7.  Cliquez avec le bouton droit sur le nom de domaine SIP, puis cliquez sur **nouvel hôte (A ou AAAA)**.

8.  Dans **nom**, tapez lyncdiscoverinternal comme nom d’hôte de l’URL du service de découverte automatique interne.

9.  Dans **adresse IP**, tapez l’adresse IP des services Web internes du directeur (ou, si vous utilisez un équilibreur de charge, tapez l’adresse IP virtuelle du directeur de charge). Comme indiqué à l’étape 4, si vous n’utilisez pas de réalisateur, il est possible que vous deviez entrer l’adresse IP du serveur frontal ou du serveur Standard Edition ou, si vous utilisez un équilibreur de charge, tapez l’adresse IP de l’équilibrage de charge du pool frontal.

10. Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.

11. Pour créer un enregistrement A ou AAAA supplémentaire, répétez les étapes 8 à 10, en gardant à l’esprit que vous devez créer de nouveaux enregistrements de découverte automatique A ou AAAA dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync Server 2013.

12. Lorsque vous avez terminé de créer un (pour les enregistrements IPv6, AAAA), cliquez sur **terminé**.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Création d’un enregistrement DNS externe

1.  Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public, puis suivez les étapes ci-dessous. Nous ne sommes pas en mesure de décrire exactement l’endroit où se trouvent les éléments de l’environnement de votre fournisseur DNS, car il existe peut-être différentes manières de gérer votre DNS externe, mais nous espérons pouvoir suivre ces étapes.

2.  Vous devez être connecté en tant que compte qui peut créer des enregistrements DNS dans cet environnement.

3.  Dans le cas d’un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com). Dans le cas d’un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).

4.  Vous devez déjà voir l’enregistrement d’un hôte A (AAAA pour IPv6) pour votre pool de répertoires (par exemple, lyncwebexdir01.contoso.com), vous devez donc confirmer qu’il est présent et quel est l’adresse IP. Si ce n’est pas le cas, il est possible que vous n’utilisiez pas un pool de réalisateurs. Si tel est le cas, vous devez utiliser l’adresse IP de votre pool frontal, ou si vous effectuez cette opération pour un serveur unique pour votre serveur frontal ou Standard Edition Server. Gardez à l’esprit que vos serveurs sont également situés derrière un équilibreur de charge ou en utilisant un proxy inverse. Notez également les adresses IP pour pouvoir suivre les étapes ci-dessous.

5.  Vous devez également vérifier qu’un enregistrement hôte A (AAAA pour IPv6) existe pour votre nom de domaine complet (FQDN) de votre liste de serveurs Web externes (par exemple, lyncwebextpool01.contoso.com) ou une adresse IP pour votre installation de Lync Server unique si vous Aucun pool frontal. Comme indiqué à l’étape précédente, vous devez disposer de ce qui suit si vous n’avez pas de pool de directeurs.

6.  À présent, dans le format approprié pour votre fournisseur DNS externe, choisissez l’option de création d’un **nouvel hôte a ou AAAA** (il s’agit d’une option de menu ou d’un lien, selon le format du fournisseur DNS).

7.  Il doit y avoir un lieu pour entrer un **nom**, tapez lyncdiscover comme nom d’hôte de l’URL du service de découverte automatique externe.

8.  Il devrait également y avoir une zone de texte **adresse IP** , vous devez entrer l’adresse IP (par exemple, lyncwebexdir01.contoso.com) ou éventuellement l’adresse IP du système d’équilibrage de charge (ou une adresse IP de proxy inverse), puis cliquer sur OK ou exécuter une action quelconque du DNS externe pour accepter la création de cette entrée. Comme indiqué à l’étape 4, si vous n’avez pas de pool de répertoires, vous devez utiliser l’adresse IP du pool frontal ou l’adresse IP d’un serveur configuré, selon le cas.

9.  Vous devez effectuer une nouvelle découverte automatique A ou un enregistrement AAAA dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

