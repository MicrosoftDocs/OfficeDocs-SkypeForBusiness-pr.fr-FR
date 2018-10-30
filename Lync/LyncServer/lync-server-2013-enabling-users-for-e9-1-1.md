---
title: 'Lync Server 2013 : Activation des utilisateurs pour E9-1-1'
TOCTitle: Activation des utilisateurs pour E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425892(v=OCS.15)
ms:contentKeyID: 49296957
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation des utilisateurs pour E9-1-1 dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-06-06_

Lors de l’inscription du client, Lync Server utilise une stratégie d’emplacement pour configurer les propriétés du service Enhanced 9-1-1 pour les utilisateurs activés pour la Voix Entreprise. Par exemple, la stratégie d’emplacement contient des informations, telle que la chaîne de numérotation d’urgence, et indique si un utilisateur doit entrer manuellement ou non un emplacement si le service d’informations sur l’emplacement n’en fournit pas un automatiquement. Pour obtenir une définition complète d’une stratégie d’emplacement, reportez-vous à [Définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Lync Server peut affecter une stratégie d’emplacement aux clients basés sur un sous-réseau ou aux utilisateurs soumis à une stratégie globale, par site et par utilisateur. Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.

  - **Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**  
    Vous pouvez affecter un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale. Cependant, en affectant une stratégie d’emplacement à un site réseau Lync Server et en ajoutant ensuite des sous-réseaux au site, vous pouvez limiter la prise en charge du service E9-1-1 à certains emplacements de l’entreprise et spécifier le comportement de routage E9-1-1 par site.

<!-- end list -->

  - **Envisagez-vous d’activer des utilisateurs individuels au moyen d’une stratégie utilisateur ?**  
    Vous pouvez affecter directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.

<!-- end list -->

  - **Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, ces clients doivent-ils bénéficier du service E9-1-1 ?**  
    Si une stratégie d’emplacement globale, de site ou d’utilisateur est affectée aux utilisateurs, ils peuvent être appelés à entrer un emplacement dans le client si celui-ci est en dehors d’un sous-réseau défini ou si aucun emplacement n’a été trouvé par le service d’informations sur l’emplacement. Pour plus d’informations, reportez-vous à [Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

