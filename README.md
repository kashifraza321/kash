# kash

/* Not sure what to do with these code snippets? See: https://www.thathandsomebeardedguy.com/what-do-i-do-with-these-code-snippets/ */

add_filter( 'wc_stripe_require_3ds', 'handsome_beardedguy_maybe_force_3ds', 10, 2 );

function handsome_beardedguy_maybe_force_3ds( $required, $source_object ) {
	return ( is_object( $source_object ) && property_exists( $source_object, 'card' ) && 'optional' === $source_object->card->three_d_secure ) ? true : $required;
}
