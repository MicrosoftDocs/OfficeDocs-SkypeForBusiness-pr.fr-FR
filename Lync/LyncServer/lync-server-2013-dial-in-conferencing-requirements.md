---
title: Configuration requise pour les conférences rendez-vous dans Lync Server 2013
TOCTitle: Configuration requise pour les conférences rendez-vous dans Lync Server 2013
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398802(v=OCS.15)
ms:contentKeyID: 49298323
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour les conférences rendez-vous dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-30_

Avant de démarrer le processus de déploiement du Lync Server 2013, vous devez planifier les points suivants :

  - la configuration à utiliser pour se connecter au réseau téléphonique commuté (RTC) ;

  - votre stratégie d’affectation de régions de conférence rendez-vous aux numéros d’accès entrants ;

  - votre stratégie de création d’annuaires de conférence.

## Planification de la connectivité PSTN pour conférence rendez-vous

La conférence rendez-vous nécessite au moins un serveur de médiation et au moins une passerelle PSTN.

Vous pouvez déployer un serveur de médiation dans un site central ou dans un site de succursale. Dans un site central, vous pouvez colocaliser un serveur de médiation sur un pool de serveurs frontaux ou un serveur Standard Edition, ou vous pouvez le déployer sur un serveur ou un pool autonome. Dans un site de succursale, vous pouvez déployer un serveur de médiation sur un serveur autonome ou comme composant du Survivable Branch Appliance.

Vous pouvez déployer une passerelle PSTN dans un site central ou dans un site de succursale. Dans un site de succursale, la passerelle PSTN peut être autonome ou un composant du Survivable Branch Appliance.

> [!NOTE]  
> La conférence rendez-vous ne fait pas appel au contournement de média, car le serveur de conférence A/V ne prend pas en charge cette fonction.

Pour plus d’informations sur la planification de votre configuration du serveur de médiation et des passerelles PSTN pour les conférences rendez-vous, voir [Composants et topologies utilisés pour le serveur de médiation dans Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) dans la documentation de planification.

## Planification des régions de conférence rendez-vous

Lors de la configuration des conférences rendez-vous, vous créez des plans de numérotation et des numéros d’accès à ces conférences. Les plans de numérotation représentent des ensembles de règles de normalisation qui spécifient le nombre et la séquence de chiffres d’un numéro de téléphone et qui transposent ce numéro au format E.164 standard de routage des appels. Les numéros d’accès aux conférences rendez-vous sont les numéros que les participants composent pour accéder à une conférence.

Tout numéro d’accès à une conférence rendez-vous doit être associé à au moins un plan de numérotation. Les régions de conférence rendez-vous associent un numéro d’accès à ses plans de numérotation. Lorsque vous établissez un plan de numérotation, vous spécifiez la région de conférence rendez-vous qui s’applique au plan de numérotation. Quand vous créez le numéro d’accès à la conférence rendez-vous, vous sélectionnez les régions qui associent le numéro d’accès aux plans de numérotation appropriés.

Lorsque vous créez un plan de numérotation, vous spécifiez son étendue : étendue d’utilisateur, de pool ou de site. Chaque utilisateur est associé au plan de numérotation dans l’étendue la plus restreinte applicable à son cas. Par exemple, un utilisateur est affecté à un plan de numérotation de niveau utilisateur, si applicable. Si aucun plan de numérotation de niveau utilisateur ne s’applique, l’utilisateur est affecté à un plan de numérotation au niveau du pool. Si aucun plan de numérotation au niveau du pool ne s’applique, l’utilisateur est affecté à un plan de numérotation au niveau du site. Si aucun plan de numérotation au niveau du site ne s’applique, l’utilisateur est affecté à un plan de numérotation global.

Avant de configurer les plans de numérotation, il est important de planifier le mode d’attribution de nom des régions et l’utilisation des régions. Les considérations suivantes s’appliquent aux régions de conférence rendez-vous :

  - Une région constitue généralement une zone géographique associée à un bureau ou un groupe de bureaux.

  - Des langues sont associées aux numéros d’accès aux conférences rendez-vous. Si vous prenez en charge des zones géographiques comprenant plusieurs langues, vous devez décider du mode de définition des régions pour prendre en charge les différentes langues. Par exemple, vous pouvez définir plusieurs régions en associant une zone géographique et une langue, ou vous pouvez définir une seule région en fonction de la zone géographique et disposer de différents numéros d’accès aux conférences rendez-vous pour chaque langue.

  - Lorsqu’un utilisateur programme une réunion, par défaut, cette dernière utilise la région spécifiée dans le plan de numérotation de cet utilisateur.

  - Par défaut, tous les numéros d’accès aux conférences rendez-vous de la région sont inclus dans l’invitation à la réunion.

  - Il est important de nommer les régions de manière explicite. L’utilisateur peut recourir aux noms pour modifier une région de réunion afin que les différents numéros d’accès soient inclus dans l’invitation. (Lorsqu’un utilisateur emploie Outlook pour planifier une réunion, il fait appel au complément de réunion en ligne pour Lync 2013 pour modifier la région).

  - Les régions doivent être désignées de telle manière que tout invité souhaitant accéder à une conférence puisse visualiser un numéro d’accès local dans l’invitation.

  - Vous pouvez configurer l’ordre d’affichage des numéros d’accès au sein d’une région dans la page Paramètres de conférence rendez-vous (cela affecte également leur ordre d’affichage dans l’invitation à la conférence) en utilisant les applets de commande Lync Server Management Shell.

  - Un utilisateur peut composer un numéro d’accès pour participer à une conférence rendez-vous en tout point du globe.

## Planification des annuaires des conférences

Les annuaires des conférences gèrent la mise en correspondance de l’ID alphanumérique de la réunion qu’un participant utilise pour accéder à la conférence lorsqu’il exécute Lync 2013 et l’ID de conférence composé exclusivement de chiffres qu’un participant utilise pour accéder à une conférence rendez-vous. Le format de l’ID de conférence est le suivant :

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

La création de plusieurs annuaires des conférences permet de s’assurer que les ID de conférences restent courts jusqu’à ce qu’une quantité importante de conférences aient été créées. Dans une organisation avec un nombre type de conférences par utilisateur, nous vous conseillons de créer un annuaire des conférences ne dépassant pas 999 utilisateurs dans le pool. Le respect de cette consigne permet en général de limiter la longueur des ID de conférences. Cependant, une fois que le nombre d’annuaires de conférences (parmi tous les pools) dépasse 9, le numéro d’ID de conférence augmente afin de prendre en charge des conférences supplémentaires.

## Voir aussi

#### Concepts

[Composant Serveur de médiation dans Lync Server 2013](lync-server-2013-mediation-server-component.md)  
[Plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

