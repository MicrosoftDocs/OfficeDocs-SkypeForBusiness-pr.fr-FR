---
title: "Lync Server 2013 : Conc. des flux d’appels du syst. de rép. vocale interactive"
TOCTitle: Conception des flux d’appels du système de réponse vocale interactive
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413020(v=OCS.15)
ms:contentKeyID: 49299346
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conception des flux d’appels du système de réponse vocale interactive dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-25_

Vous pouvez utiliser la réponse vocale interactive (IVR) pour obtenir des informations des appelants et acheminer l’appel jusqu’à la file d’attente appropriée. Les paires de questions et réponses déterminent la file d’attente à utiliser. Selon la réponse de l’appelant, celui-ci entend une question de suivi ou est acheminé vers la file d’attente appropriée. Les questions du système de réponse vocale interactive ainsi que les réponses de l’appelant sont fournies à l’agent qui prend l’appel, fournissant des informations précieuses à l’agent.

## Vue d’ensemble des fonctionnalités du système de réponse vocale interactive

L’application Response Group offre des fonctions de reconnaissance vocale et de conversion de texte par synthèse vocale en 26 langues. Vous pouvez entrer les questions du système de réponse vocale interactive à l’aide de la conversion de texte par synthèse vocale, d’un fichier wave (.wav) ou d’un fichier audio Windows Media (.wma). Les appelants peuvent répondre à l’aide de la voix ou de réponses de numérotation en fréquences vocales (DTMF).

Les flux de travail interactifs prennent en charge jusqu’à deux niveaux de questions, chaque question et, selon la réponse de l’appelant, le système de réponse vocale interactive pose à l’appelant une question avec quatre réponses possibles, et selon la réponse de l’appelant, l’achemine vers une file d’attente ou lui pose une deuxième question. Quatre réponses sont également possibles pour la deuxième question. Selon la réponse à la question de second niveau, l’appelant est acheminé vers la file d’attente appropriée.

> [!NOTE]  
> Lorsque vous concevez des flux d’appels à l’aide de Lync Server Management Shell, vous pouvez définir autant de niveaux de questions du système de réponse vocale interactive et de réponses que vous le souhaitez. Cependant, pour faciliter l’utilisation par l’appelant, nous vous conseillons de vous limiter à trois niveaux de questions et cinq réponses par niveau. En outre, si vous concevez un flux d’appels qui comprend plus de deux niveaux de questions avec plus de quatre réponses possibles à chaque fois, vous ne pourrez pas modifier le flux d’appels à l’aide du Panneau de configuration Lync Server 2013.

Les questions du système de réponse vocale interactive ainsi que les réponses de l’appelant sont fournies à l’agent qui répond en acceptant l’appel.

## Utilisation des technologies vocales

Les technologies vocales, telles que la reconnaissance vocale et la conversion de texte par synthèse vocale, peuvent améliorer le produit et permettre aux gens d’accéder aux informations de façon plus naturelle et plus efficace. Cependant, il peut arriver que le texte spécifié ou la réponse vocale de l’utilisateur ne soit pas correctement reconnu par le moteur de synthèse vocale. Par exemple, le moteur de synthèse vocale convertit le symbole « \# » par le mot « numéro ». Ce problème peut être atténué en procédant comme suit :

  - Le moteur de synthèse vocale autorise cinq tentatives de réponse. Si la réponse de l’appelant est incorrecte (autrement dit, si elle ne figure pas parmi les réponses spécifiées) ou s’il ne fournit aucune réponse, l’appelant se voit offrir une autre opportunité de fournir la bonne réponse. L’appelant peut donner cinq réponses avant d’être déconnecté si aucune d’elles n’est correcte. Vous pouvez configurer le système de réponse vocale interactive pour qu’il lise un message personnalisé après chaque erreur de l’appelant. La question est répétée à chaque fois.

  - Pour réduire le risque que le moteur de synthèse vocale n’interprète le bruit ambiant comme une réponse, utilisez des réponses plus longues. Par exemple, les réponses doivent comprendre plusieurs syllabes et être significativement différentes à l’oreille les unes des autres.

  - Si vos questions présentent à la fois des réponses vocales et DTMF, configurez les réponses vocales en utilisant des mots qui représentent le concept plutôt que la réponse DTMF. Par exemple, plutôt que d’utiliser « Appuyez ou dites un », utilisez « Appuyez sur 1 ou dites facturation ».

  - Après avoir conçu votre système de réponse vocale interactive, appelez le flux de travail, écoutez les invites, répondez à chacune d’elles à l’aide de la voix et vérifiez que le système de réponse vocale interactive se présente et se comporte comme prévu. Vous pouvez ensuite modifier le système de réponse vocale interactive afin de résoudre des problèmes liés à l’interprétation. Dans le cadre de notre exemple précédent, si vous devez faire référence à la touche \#, vous pouvez réécrire votre invite de réponse vocale interactive pour qu’elle utilise le nom de la touche au lieu du symbole \#. Par exemple, « Pour être mis en relation avec le service commercial, appuyez sur la touche dièse ».

## Exemples de conception IVR

Les sections suivantes contiennent des exemples de différents scénarios de réponse vocale interactive et de paires de questions-réponses.

## Système de réponse vocale interactive avec un niveau de questions

L’exemple suivant illustre un système de réponse vocale interactive utilisant un niveau de questions. Il utilise la reconnaissance vocale pour détecter la réponse de l’appelant.

**Question :** « Merci d’appeler le service des ressources humaines. Si vous souhaitez parler à une personne de l’équipe qui traite les salaires, dites salaire. Sinon, dites RH. »

  - **L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe en charge des salaires.

  - **L’option 2 est sélectionnée :** l’appelant est dirigé vers l’équipe des ressources humaines.

L’illustration suivante montre le flux d’appels.

**Flux d’appels pour un modèle interactif à un niveau**

![Concevoir des flux d’appels à l’aide du système de réponse vocale interactive](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Concevoir des flux d’appels à l’aide du système de réponse vocale interactive")

## Système de réponse vocale interactive avec deux niveaux de questions

L’exemple suivant illustre un système de réponse vocale interactive utilisant deux niveaux de questions. Il permet aux appelants de répondre à l’aide de la voix ou de la numérotation en fréquences vocales (DTMF).

**Question :** « Merci d’appeler le support technique informatique. Si vous rencontrez un problème d’accès réseau, appuyez sur 1 ou dites « réseau ». Si vous rencontrez un problème de logiciel, appuyez sur 2 ou dites « logiciel ». Si vous rencontrez un problème de matériel, appuyez 3 ou dites « matériel ». »

  - **L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe de gestion du réseau.

  - **L’option 2 est sélectionnée :** une question de suivi est posée à l’appelant :
    
    **Question :** « S’il s’agit d’un problème lié au système d’exploitation, appuyez sur 1 ou dites « système d’exploitation ». S’il s’agit d’un problème avec une application interne, appuyez sur 2 ou dites « application interne ». Sinon, appuyez sur 3 ou dites « autre ». »
    
      - **L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des systèmes d’exploitation.
    
      - **L’option 2 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des applications internes.
    
      - **L’option 3 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des logiciels.

  - **L’option 3 est sélectionnée :** une question de suivi est posée à l’appelant :
    
    **Question :** « S’il s’agit d’un problème d’imprimante, appuyez sur 1. Sinon, appuyez sur 2. »
    
      - **L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des imprimantes.
    
      - **L’option 2 est sélectionnée :** l’appelant est dirigé vers l’équipe de support du matériel.

L’illustration suivante montre le flux d’appels.

**Flux d’appels pour un modèle interactif à deux niveaux**

![Concevoir des flux d’appels à l’aide du système de réponse vocale interactive](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Concevoir des flux d’appels à l’aide du système de réponse vocale interactive")

## Meilleures pratiques

La liste suivante décrit certaines meilleures pratiques lorsque vous concevez votre système de réponse vocale interactive :

  - Permettez à l’appelant d’accéder rapidement à la tâche. Évitez de mettre trop d’informations ou de longs messages marketing dans votre système de réponse vocale interactive.

  - Si vous souhaitez inclure un long message, envisagez de l’intégrer à la première question plutôt qu’au message d’accueil. Les appelant peuvent contourner le message s’il fait partie de la première question en répondant à la question, mais ils ne peuvent pas contourner le message d’accueil.

  - Parlez dans la langue de l’appelant. Évitez le langage emprunté. Parlez naturellement.

  - Écrivez des invites efficaces. Supprimez toutes les options inutiles. Structurez les informations afin que la réponse attendue de l’appelant soit à la fin de la phrase. Par exemple, « Pour parler à l’équipe commerciale, appuyez sur 1 ».

  - Rendez les réponses vocales conviviales pour l’appelant. Par exemple, si vous spécifiez des réponses vocales et DTMF, utilisez quelque chose comme : « Pour parler à l’équipe commerciale, appuyez sur 1 ou dites commercial. »

  - Testez le système de réponse vocale interactive sur un groupe d’utilisateurs avant de le déployer dans votre organisation.

