---
title: 'Lync Server 2013 : Définition de la stratégie d’emplacement'
TOCTitle: Définition de la stratégie d’emplacement
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398962(v=OCS.15)
ms:contentKeyID: 49299050
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la stratégie d’emplacement pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-29_

Chaque stratégie d’emplacement renferme les informations suivantes :

  - **Services d’urgence activés**  
    Si cette valeur est **Oui**, le client est activé pour E9-1-1. Lorsqu’un client s’inscrit, il tente d’obtenir un emplacement du service d’informations sur l’emplacement et inclura les informations d’emplacement dans un appel d’urgence.

<!-- end list -->

  - **Emplacement requis**  
    Ce paramètre est uniquement utilisé lorsque l’option **Services d’urgence activés** est définie sur **Oui**.
    
    Vous pouvez configurer le paramètre **Emplacement requis** pour définir le comportement du client. Si vous sélectionnez **Non**, l’utilisateur ne sera pas invité à entrer un emplacement. Si vous sélectionnez **Oui**, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite. Si vous sélectionnez **Clause d’exclusion de responsabilité**, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera également s’il essaie d’ignorer le message d’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.
    
    > [!NOTE]  
    > Le texte de la clause d’exclusion de responsabilité ne s’affiche pas si un utilisateur a entré manuellement un emplacement avant d’avoir été activé pour E9-1-1. Les mises à jour apportées à ce texte ne s’afficheront pas pour les utilisateurs ayant déjà pris connaissance de la clause d’exclusion de responsabilité.

<!-- end list -->

  - **Clause d’exclusion de responsabilité du service d’urgence**  
    Ce paramètre spécifie la clause d’exclusion de responsabilité qui s’affiche si les utilisateurs ignorent l’invite pour un emplacement. Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour définir différentes clauses d’exclusion de responsabilité pour différents paramètres régionaux ou ensembles d’utilisateurs.
    
    > [!NOTE]  
    > Ce paramètre de stratégie d’emplacement diffère de Lync Server 2010, où vous utilisez l’applet de commande <strong>Set-CsEnhancedEmergencyServiceDisclaimer</strong> pour définir une clause d’exclusion de responsabilité pour l’ensemble de l’organisation. Si une clause d’exclusion de responsabilité globale existe déjà, vous devez spécifier cette clause dans la stratégie d’emplacement. En d’autres termes, Lync Server 2013 n’utilise que les clauses d’exclusion de responsabilité spécifiées dans la stratégie d’emplacement.

<!-- end list -->

  - **Chaîne de numérotation d’urgence**  
    La chaîne de numérotation (moins le « + » de début, mais comprenant toute normalisation apportée par le plan de numérotation de l’utilisateur Lync) signale qu’un appel est un appel d’urgence. La **chaîne de numérotation d’urgence** oblige le client à inclure dans l’appel les informations d’emplacement et de rappel.
    
    > [!NOTE]  
    > Si votre organisation n’utilise pas de préfixe d’accès aux lignes externes, vous n’avez pas besoin de créer de règle de normalisation de plan de numérotation qui ajoute un « + » à la chaîne 911 avant d’envoyer l’appel au routage sortant sur un serveur de pool Lync. Le « + » sera automatiquement ajouté au début par le client Lync comme résultat de la stratégie d’emplacement. Cependant, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de plan de numérotation applicable qui supprime le préfixe d’accès externe et ajoute le « + ». Par exemple, si votre emplacement utilise comme préfixe d’accès externe 9 et qu’un utilisateur compose le 9 911 pour passer un appel d’urgence, le client utilisera sa stratégie de plan de numérotation pour normaliser cette chaîne en +911 avant que le numéro composé soit évalué par les itinéraires dans le profil d’emplacement de l’appelant.

<!-- end list -->

  - **Masques de la chaîne de numérotation d’urgence**  
    Liste de chaînes de numérotation séparées par des points-virgules convertie en **chaîne de numérotation d’urgence** spécifiée. Par exemple, vous pouvez ajouter le 112 (numéro de services d’urgence pour la plupart des pays européens). Un utilisateur Lync européen en visite peut ignorer que le 911 est le numéro d’urgence aux États-Unis. Il peut tout de même composer le 112 et obtenir le même résultat. Comme pour la chaîne de numérotation d’urgence, n’incluez pas de « + » avant chaque numéro, et si vous utilisez des codes d’accès aux lignes externes, assurez-vous de la présence de règles de normalisation dans la stratégie de plan de numérotation de l’utilisateur pour supprimer le chiffre de code d’accès.

<!-- end list -->

  - **Utilisation RTC**  
    Nom de l’utilisation RTC qui contient les chemins de routage qui déterminent la jonction SIP, la passerelle RTC ou la passerelle ELIN vers laquelle les appels seront acheminés.
    
    > [!NOTE]  
    > Seule une utilisation peut être affectée à une stratégie d’emplacement. Cette utilisation RTC remplace les utilisations RTC affectées à la stratégie de voix de l’utilisateur, mais s’applique uniquement aux appels passés à la chaîne de numérotation d’urgence ou à l’un des masques de chaîne de numérotation d’urgence.

<!-- end list -->

  - **URI de notification**  
    Indique les URI SIP des membres du personnel de sécurité qui reçoivent une notification de messagerie instantanée en cas d’appel d’urgence. Les groupes de distribution sont pris en charge.

<!-- end list -->

  - **Conference URI**  
    Indique le numéro SDA (en général, numéro de service de sécurité) qui doit participer à la conférence en cas d’appel d’urgence.

<!-- end list -->

  - **Mode Conférence**  
    Indique si l’URI de conférence participera à l’appel d’urgence via une communication unidirectionnelle ou bidirectionnelle.

<!-- end list -->

  - **Intervalle d’actualisation d’emplacement**  
    Indique la durée (en heures) entre les demandes clientes pour la mise à jour de l’emplacement du service d’informations sur l’emplacement. La valeur peut être comprise entre 1 et 12. La valeur par défaut est 4.

