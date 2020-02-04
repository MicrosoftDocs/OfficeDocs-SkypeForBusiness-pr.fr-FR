---
title: Configuration requise pour les conférences rendez-vous Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c54e162aeda43730dea471732124023588e9041
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Configuration requise pour les conférences rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Avant de démarrer le processus de déploiement de Lync Server 2013, vous devez planifier les opérations suivantes :

  - Configuration à utiliser pour la connexion au réseau téléphonique public commuté (RTC)

  - Votre stratégie d’affectation de zones de conférence rendez-vous à des numéros d’accès rendez-vous

  - Votre stratégie de création d’annuaires de conférences

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>Planification de la connectivité PSTN rendez-vous

La Conférence rendez-vous requiert au moins un serveur de médiation et au moins une passerelle PSTN.

Vous pouvez déployer un serveur de médiation dans un site central ou dans un site de succursale. Dans un site central, vous pouvez colocaliser un serveur de médiation sur un pool frontal ou un serveur Standard Edition ou vous pouvez le déployer sur un serveur ou un pool autonome. Dans un site de succursale, vous pouvez déployer un serveur de médiation sur un serveur autonome ou comme composant du serveur Survivable Branch Appliance.

Vous pouvez déployer une passerelle RTC dans un site central ou dans un site de succursale. Dans un site de succursale, la passerelle RTC peut être autonome ou un composant Survivable Branch Appliance.

<div>


> [!NOTE]  
> La fonction de conférence rendez-vous n’utilise pas le recours au contenu multimédia, car le serveur de conférence A/V ne prend pas en charge la dérivation multimédia.



</div>

Pour plus d’informations sur la planification de votre configuration du serveur de médiation et des passerelles RTC pour les conférences rendez-vous, voir [composants et topologies du serveur de médiation dans Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>Planification des régions de conférence rendez-vous

Lors de la configuration d’un rendez-vous, vous créez des plans de numérotation et des numéros d’accès pour les conférences rendez-vous. Le plan de numérotation est un ensemble de règles de normalisation qui spécifient le nombre et le modèle de chiffres d’un numéro de téléphone et traduisant ce numéro de téléphone dans le format E. 164 standard pour le routage des appels. Les numéros d’accès aux conférences rendez-vous sont les numéros que les participants composent pour accéder à une conférence.

Tout numéro d’accès à une conférence rendez-vous doit être associé à au moins un plan de numérotation. Régions de conférence rendez-vous associez un numéro d’accès à une conférence rendez-vous à ses plans de numérotation. Lorsque vous configurez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation. Quand vous créez le numéro d’accès à la conférence rendez-vous, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.

Lorsque vous créez un plan de numérotation, vous spécifiez l’étendue du plan de numérotation : étendue des utilisateurs, étendue du pool ou étendue du site. Chaque utilisateur est associé au plan de numérotation dans l’étendue la plus restreinte applicable à son cas. Par exemple, un utilisateur est affecté à un plan de numérotation de niveau utilisateur, le cas échéant. Si aucun plan de numérotation de niveau utilisateur ne s’applique, l’utilisateur est affecté à un plan de numérotation au niveau du pool. Si aucun plan de numérotation au niveau du pool ne s’applique, l’utilisateur est affecté à un plan de numérotation au niveau du site. Si aucun plan de numérotation au niveau du site ne s’applique, l’utilisateur est affecté à un plan de numérotation global.

Avant de configurer les plans de numérotation, il est important de planifier le mode d’attribution de nom des régions et l’utilisation des régions. Les considérations suivantes s’appliquent aux régions de conférence rendez-vous :

  - Une région constitue généralement une zone géographique associée à un bureau ou à un groupe de bureaux.

  - Des langues sont associées aux numéros d’accès aux conférences rendez-vous. Si vous prenez en charge des zones géographiques comprenant plusieurs langues, vous devez déterminer le mode de définition des régions pour prendre en charge les différentes langues. Par exemple, vous pouvez définir différentes régions en associant une zone géographique et une langue ou définir une seule région en fonction de la zone géographique et disposer de différents numéros d’accès aux conférences rendez-vous pour chaque langue.

  - Lorsqu’un utilisateur programme une réunion, par défaut, cette dernière utilise la région spécifiée dans le plan de numérotation de cet utilisateur.

  - Par défaut, tous les numéros d’accès rendez-vous de la région sont inclus dans l’invitation à la réunion.

  - Il est important de nommer les régions de manière explicite. L’utilisateur peut recourir aux noms pour modifier une région de réunion afin que les différents numéros d’accès soient inclus dans l’invitation. (Lorsque les utilisateurs utilisent Outlook pour planifier une réunion, l’utilisateur utilise le complément réunion en ligne pour Lync 2013 pour modifier la région).

  - Les régions doivent être désignées de sorte que tout invité souhaitant accéder à une conférence puisse visualiser un numéro d’accès local dans l’invitation.

  - Vous pouvez configurer l’ordre dans lequel les numéros d’accès au sein d’une région apparaissent sur la page Paramètres de conférence rendez-vous (et, par conséquent, l’ordre dans lequel ils apparaissent dans l’invitation à la Conférence) en utilisant des applets de commande Lync Server Management Shell.

  - Un utilisateur peut composer un numéro d’accès pour participer à une conférence rendez-vous en tout point du globe.

</div>

<div>

## <a name="planning-for-conference-directories"></a>Planification des annuaires de conférences

Les annuaires de conférences maintiennent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence lors de l’utilisation de la 2013 Lync et l’ID de conférence numérique uniquement qu’un participant à la Conférence rendez-vous utilise pour rejoindre la Conférence. Le format de l’ID de conférence est le suivant :

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

La création de différents annuaires des conférences permet de s’assurer que les ID de conférences restent courts jusqu’à ce qu’une quantité importante de conférences ait été créée. Dans une organisation avec un nombre type de conférences par utilisateur, il est recommandé de créer un annuaire des conférences ne dépassant pas 999 utilisateurs dans le pool. Dans cette règle, les ID de conférence peuvent généralement être conservés de petite taille. Cependant, lorsque le nombre d’annuaires de conférences (tous pools confondus) dépasse 9, la longueur de l’ID de conférence augmente pour permettre la prise en charge de conférences supplémentaires.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Composant serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

