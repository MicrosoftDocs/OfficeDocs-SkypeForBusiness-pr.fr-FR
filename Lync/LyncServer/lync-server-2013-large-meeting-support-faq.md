---
title: "FAQ sur la prise en charge des grandes réunions Lync Server 2013"
TOCtitle: "FAQ sur la prise en charge des grandes réunions Lync Server 2013"
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204804(v=OCS.15)
ms:contentKeyID: 49296832
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Forum aux questions sur la prise en charge des grandes réunions Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-22_

Les sections suivantes apportent des réponses aux questions fréquemment posées sur la création et l’exécution de grandes réunions.

## Q : Combien d’utilisateurs peuvent participer à une grande réunion ?

Le modèle d’utilisateur Lync Server spécifie une limite de 250 utilisateurs pour un pool partagé ou de 1 000 utilisateurs pour un pool consacré aux grandes réunions, mais ces chiffres ne représentent que le nombre d’utilisateurs que nous avons testés, et uniquement pour la configuration matérielle utilisée dans notre test. Ces limites maximales sont donc recommandées par rapport à ce test. Toutefois, vous contrôlez le nombre réel de participants aux réunions dans votre organisation en configurant une ou plusieurs stratégies de conférence (à l’aide des applets de commande Windows PowerShell dans Lync Server Management Shell ou à partir du Panneau de configuration Lync Server). Le nombre spécifié dans une stratégie de conférence peut être tout nombre entier 32 bits compris entre 1 et 4 294 967 295, mais la taille recommandée est comprise entre 2 et 250 participants, inclus. La valeur par défaut est 250.

## Q : Combien de réunions ou autres charges de travail puis-je avoir dans un pool dédié aux grandes réunions ?

Pour garantir la meilleure expérience utilisateur dans les grandes réunions d’un maximum de 1 000 participants, nous vous conseillons d’héberger sur un pool dédié aux grandes réunions une seule grande réunion à la fois. Il est aussi préférable de ne pas autoriser l’exécution d’autres charges de travail sur ce pool pendant le déroulement d’une grande réunion.

## Q : Les organisateurs de grandes réunions doivent-ils être hébergés sur le pool dédié ?

Non. Nous ne recommandons pas d’héberger sur le pool dédié des utilisateurs autres que le personnel dédié à la planification des grandes réunions. Cela permet d’éviter que les grandes réunions hébergées dans le pool ne soient affectées par le trafic d’autres communications en temps réel. Vous devez planifier les grandes réunions sur le pool dédié à l’aide d’un compte d’utilisateur appartenant à un membre du personnel chargé de la planification des grandes réunions. Vous devez ajouter le compte d’utilisateur de l’organisateur de la réunion (celui qui sollicite la grande réunion) en tant que présentateur de la grande réunion.

## Q : Quelles modalités multimédias puis-je utiliser dans une grande réunion ?

Les grandes réunions de plus de 1 000 utilisateurs peuvent inclure de l’audio, de la vidéo, un partage PowerPoint, des tableaux blancs et l’interrogation de présence.

## Q : Puis-je utiliser la messagerie instantanée de groupe dans les grandes réunions ?

Oui. Toutefois, un grand nombre de messages instantanés, en particulier quand ils sont envoyés par un grand nombre de participants à la réunion, peuvent affecter l’expérience utilisateur en raison des problèmes liés au défilement rapide du texte dans la fenêtre de messagerie instantanée. La distribution d’un grand nombre de messages instantanés à un groupe de 1 000 utilisateurs peut également introduire des charges de serveur considérable, et ainsi nuire aux performances. En règle générale, la messagerie instantanée n’est requise que pour les questions et réponses.

## Q :Les utilisateurs peuvent-ils participer à de grandes réunions en composant le numéro à partir d’un téléphone ?

Oui. Si le pool Lync Server 2013 est correctement déployé et activé pour la conférence rendez-vous, les utilisateurs ont la possibilité de participer à des grandes réunions en composant un numéro. Nos tests ont montré que jusqu’à 15 % de 1 000 participants peuvent participer à une grande réunion pendant 10 minutes.

## Q : Puis-je héberger des grandes réunions dans une topologie virtuelle ?

Nous n’avons pas testé de grandes réunions dans une topologie virtuelle, nous ne sommes donc pas en mesure d’assurer un support en cas d’utilisation d’ordinateurs virtuels pour héberger un pool dédié aux grandes réunions.

