---
title: Configuration requise pour la Conférence rendez-vous Lync Server 2013
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
ms.openlocfilehash: b80ab9db6b565530db211db8aa47e2e00cbd9cf2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a>Exigences en matière de conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Avant de démarrer le processus de déploiement de Lync Server 2013, vous devez planifier les opérations suivantes :

  - Configuration à utiliser pour la connexion au réseau téléphonique commuté (RTC)

  - Votre stratégie d’affectation des régions de conférence rendez-vous aux numéros d’accès entrant

  - Votre stratégie de création d’annuaires de conférence

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a>Planification de la connectivité RTC rendez-vous

La Conférence rendez-vous nécessite au moins un serveur de médiation et au moins une passerelle RTC.

Vous pouvez déployer un serveur de médiation dans un site central ou dans un site de succursale. Dans un site central, vous pouvez colocaliser un serveur de médiation sur un pool frontal ou un serveur Standard Edition, ou vous pouvez le déployer sur un serveur ou un pool autonome. Dans un site de succursale, vous pouvez déployer un serveur de médiation sur un serveur autonome ou en tant que composant du Survivable Branch appliance.

Vous pouvez déployer une passerelle PSTN dans un site central ou dans un site de succursale. Dans un site de succursale, la passerelle PSTN peut être autonome ou un composant du Survivable Branch appliance.

<div>


> [!NOTE]  
> La Conférence rendez-vous n’utilise pas le contournement de média car le serveur de conférence A/V ne prend pas en charge la déviation du trafic multimédia.



</div>

Pour plus d’informations sur la planification de votre configuration pour le serveur de médiation et les passerelles PSTN pour la Conférence rendez-vous, voir [composants et topologies pour le serveur de médiation dans Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a>Planification des régions de conférence rendez-vous

Lors de la configuration d’un rendez-vous, vous créez des plans de numérotation et des numéros d’accès aux conférences rendez-vous. Les plans de numérotation sont des ensembles de règles de normalisation qui spécifient le nombre et le modèle de chiffres dans un numéro de téléphone et traduisent le numéro de téléphone au format E. 164 standard pour le routage des appels. Les numéros d’accès aux conférences rendez-vous sont les numéros que les participants participent à la Conférence.

Chaque numéro d’accès à une conférence rendez-vous doit être associé à au moins un plan de numérotation. Les régions de conférence rendez-vous associent un numéro d’accès à des conférences rendez-vous avec ses plans de numérotation. Lorsque vous configurez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation. Lorsque vous créez le numéro d’accès entrant, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.

Lorsque vous créez un plan de numérotation, vous spécifiez l’étendue du plan de numérotation : étendue utilisateur, étendue du pool ou étendue du site. Le plan de numérotation est affecté à chaque utilisateur à partir de l’étendue la plus étroite qui s’applique à l’utilisateur. Par exemple, un utilisateur est affecté à un plan de numérotation au niveau de l’utilisateur, le cas échéant. Si aucun plan de numérotation au niveau de l’utilisateur ne s’applique, un plan de numérotation au niveau du pool est affecté à l’utilisateur. Si aucun plan de numérotation au niveau du pool ne s’applique, l’utilisateur est affecté à un plan de numérotation au niveau du site. Si un plan de numérotation au niveau du site ne s’applique pas, le plan de numérotation global est affecté à l’utilisateur.

Avant de configurer les plans de numérotation, il est important de planifier la façon dont vous souhaitez nommer et utiliser des régions. Les considérations suivantes s’appliquent aux régions de conférence rendez-vous :

  - Une région est généralement une zone géographique associée à un bureau ou à un groupe de bureaux.

  - Les langues sont associées aux numéros d’accès entrant. Si vous prenez en charge les zones géographiques qui ont plusieurs langues, vous devez déterminer la manière dont vous souhaitez définir les régions afin de prendre en charge les différentes langues. Par exemple, vous pouvez définir plusieurs régions en fonction d’une combinaison de géographie et de langue, ou vous pouvez définir une région unique basée sur la géographie et disposer de différents numéros d’accès entrant pour chaque langue.

  - Lorsqu’un utilisateur planifie une réunion, par défaut, la réunion utilise la région spécifiée par le plan de numérotation de cet utilisateur.

  - Par défaut, tous les numéros d’accès entrant de la région sont inclus dans l’invitation à la réunion.

  - Il est important de nommer les régions afin qu’elles soient clairement reconnaissables. L’utilisateur peut utiliser les noms des régions pour modifier la région d’une réunion afin que différents numéros d’accès soient inclus dans l’invitation. (Lorsque les utilisateurs utilisent Outlook pour planifier une réunion, l’utilisateur utilise le complément de réunion en ligne pour Lync 2013 afin de modifier la région).

  - Les régions doivent être conçues de sorte que tout invité souhaitant accéder à une Conférence puisse voir un numéro d’accès local dans l’invitation à la Conférence.

  - Vous pouvez configurer l’ordre dans lequel les numéros d’accès au sein d’une région apparaissent sur la page Paramètres de conférence rendez-vous (et, par conséquent, l’ordre dans lequel ils apparaissent dans l’invitation à la Conférence) à l’aide des applets de commande Lync Server Management Shell.

  - Tout utilisateur de n’importe quel emplacement peut appeler n’importe quel numéro d’accès entrant pour rejoindre une conférence.

</div>

<div>

## <a name="planning-for-conference-directories"></a>Planification des annuaires de conférence

Les annuaires de conférence maintiennent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence en utilisant Lync 2013 et l’ID de conférence numérique uniquement qu’un participant de conférence rendez-vous utilise pour rejoindre la Conférence. Le format de l’ID de conférence est le suivant :

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

La création de plusieurs annuaires de conférences permet de s’assurer que les ID de conférence resteront courts jusqu’à ce qu’une quantité importante de conférences ait été créée. Dans une organisation avec un nombre classique de conférences par utilisateur, nous vous recommandons de créer un annuaire de conférences pour chaque 999 utilisateurs du pool. À l’aide de cette instruction, les ID de conférence peuvent généralement être réduits. Toutefois, une fois que le nombre d’annuaires de conférence (dans les pools) est supérieur à 9, le numéro d’identification de conférence augmentera pour prendre en charge des conférences supplémentaires.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Composant de serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

