---
title: 'Lync Server 2013 : Vue d’ensemble du parcage d’appel'
TOCTitle: Vue d’ensemble du parcage d’appel
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205124(v=OCS.15)
ms:contentKeyID: 49298239
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble du parcage d’appel dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-29_

L’application de parcage d’appelLync Server 2013 permet aux utilisateurs de Voix Entreprise d’effectuer les opérations suivantes :

  - mettre un appel en attente, puis récupérer l’appel depuis le même téléphone ou un autre téléphone ;

  - mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où il y a un téléphone de partie commune) ;

  - mettre un appel en attente et garder le téléphone d’origine libre pour répondre aux autres appels.

Lorsqu’un utilisateur parque un appel, Lync Server transfère l’appel vers un numéro temporaire, appelé *orbite* , où il est mis en attente jusqu’à ce qu’il soit récupéré ou arrive à expiration. Lync Server envoie l’orbite à l’utilisateur qui a parqué l’appel. Pour récupérer l’appel parqué, l’utilisateur peut composer le numéro de l’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation.

L’utilisateur qui a parqué un appel peut avertir quelqu’un pour récupérer l’appel en ayant recours à un mécanisme externe, tel qu’un système de messagerie instantanée ou de radiomessagerie, pour communiquer le numéro d’orbite à quelqu’un d’autre. L’utilisateur qui a parqué l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification quand l’appel est récupéré.

Du fait que les plages d’orbites sont globalement uniques, il est possible de récupérer les appels depuis n’importe quel site Lync Server ou téléphone PBX si le routage est configuré correctement. Si personne ne récupère l’appel dans un délai configurable, la personne qui l’a parqué est rappelée. Si cette personne ne répond pas au rappel, l’appel est transféré vers une destination de remplacement, telle qu’un opérateur, si la configuration est définie de la sorte. Vous pouvez configurer le nombre de sonneries de rappel avant le transfert, de une à dix. Si personne ne répond à un appel transféré, l’appel est déconnecté. L’orbite est libérée lorsque l’appel est récupéré ou déconnecté.

Quand vous déployez le parcage d’appel, vous devez réserver des plages de numéros d’extension pour le parcage des appels. Il doit s’agir d’extensions virtuelles, c’est-à-dire d’extensions auxquelles aucun utilisateur ou téléphone n’est attribué. Vous configurez ensuite la table d’orbites de parcage d’appel avec les plages de numéros d’extension, puis spécifiez quel service d’application héberge l’application de parcage d’appel qui gère chaque plage. Chaque pool frontal contient une table de parcage d’appel sur le serveur principal correspondant qui sert à gérer les appels parqués sur le pool. La liste des plages d’orbites est stockée dans le magasin central de gestion et sert à acheminer les orbites au pool de destination. Chaque pool Lync Server sur lequel est déployée et configurée l’application de parcage d’appel peut contenir plusieurs plages d’orbites. Les plages d’orbites doivent être globalement uniques dans le déploiement Lync Server.

Vous configurez également d’autres paramètres de parcage d’appel, tels que l’endroit où sont redirigés les appels s’ils arrivent à expiration et si la personne en ligne entend de la musique lorsque son appel est parqué. Vous pouvez aussi spécifier le fichier de musique à lire lorsque l’appel est en attente.

> [!NOTE]  
> Les fichiers de mise en attente musicale personnalisés pour le parcage d’appel ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence de Lync Server 2013 et sont perdus en cas d’endommagement ou d’effacement des fichiers téléchargés vers le pool. Veillez à toujours conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés que vous avez téléchargés pour le parcage d’appel.

L’application de parcage d’appel est un composant de Voix Entreprise. Cette application est installée et déployée automatiquement quand vous déployez Voix Entreprise. Cependant, avant de pouvoir utiliser le parcage d’appel, l’administrateur de Voix Entreprise doit le configurer et l’activer pour les utilisateurs via une stratégie vocale.

