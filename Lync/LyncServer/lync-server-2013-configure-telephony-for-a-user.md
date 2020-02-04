---
title: 'Lync Server 2013 : configurer la téléphonie pour un utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d57c4799c0fe9bb9dc698c3e0e74a9d73cbde524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Configurer la téléphonie pour un utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les paramètres de téléphonie sont certains des paramètres individuels d’un compte d’utilisateur qui peuvent être configurés dans le panneau de configuration de Lync Server pour l’utilisateur (autrement dit, si l’utilisateur individuel a été activé pour Lync Server 2013 et si l’Organisation prend en charge la téléphonie).

Les options de téléphonie de Lync Server pour les utilisateurs incluent les éléments suivants :

  - **Audio/vidéo désactivé**   l’utilisateur ne peut pas passer d’appels audio et vidéo.

  - **PC-à-PC seul**   l’utilisateur peut uniquement effectuer des appels audio et vidéo de PC à PC.

  - **Voix entreprise les**   utilisateurs peuvent utiliser l’infrastructure 2013 du serveur Lync pour acheminer tous les appels entrants et sortants. L’utilisateur peut également passer des appels de PC à PC.

  - **Contrôle d’appel distant**   l’utilisateur peut utiliser Lync Server 2013 pour contrôler le téléphone de bureau et peut également passer des appels de PC à PC.

Pour plus d’informations sur la configuration de la téléphonie pour une organisation, reportez-vous à la rubrique [configurer la téléphonie pour un utilisateur dans Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) et le [déploiement d’Enterprise Voice dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>Pour configurer la téléphonie pour un compte d’utilisateur spécifique

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la boîte de dialogue **Rechercher des utilisateurs** , entrez tout ou la première partie du nom complet, prénom, nom, nom du compte de comptes de sécurité, adresse SIP ou URI (Uniform Resource Identifier) du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.

5.  Dans la table, cliquez sur le compte d’utilisateur que vous voulez modifier.

6.  Dans le menu **édition** , cliquez sur **modifier**.

7.  En **téléphonie**, procédez comme suit :
    
      - Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **audio/vidéo désactivé**.
    
      - Pour activer les communications audio de PC à ordinateur pour l’utilisateur, mais pas le contrôle d’appel distant ni la voix entreprise, cliquez sur **PC à PC uniquement**. Spécifiez une valeur pour **URI ligne** pour le téléphone utilisée par l’utilisateur pour les communications audio de PC à PC.
    
      - Pour acheminer les appels téléphoniques de l’utilisateur à l’aide de l’infrastructure Lync Server 2010 conformément à la classe de la stratégie de service, y compris la communication audio entre PC et PC, cliquez sur **voix entreprise**. Dans **URI de ligne**, spécifiez le numéro de téléphone d’entreprise voix. Dans **politique de plan de numérotation** et de **stratégie vocale**, spécifiez les stratégies appropriées pour l’utilisateur. Pour spécifier les règles de normalisation pour la traduction des numéros de téléphone numérotés par l’utilisateur au format E. 164, sélectionnez le profil d’emplacement approprié dans la **politique d’emplacement**.
    
      - Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne téléphonique de bureau à partir de Lync Server 2013 pour passer des appels de PC à PC et des appels de PC à téléphone, cliquez sur **contrôle d’appel distant**. Dans **URI de ligne**, spécifiez le numéro de téléphone du contrôle d’appel distant. Pour le routage des appels, l’utilisateur doit avoir un téléphone de bureau et une connexion PBX (Private Branch Exchange).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modification des propriétés d’un compte d’utilisateur dans Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

