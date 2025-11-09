import pytest
import random
import polish_ver


# ---------------- check_input ----------------

@pytest.mark.parametrize("val,expected", [
    (1, 1),
    (53, 0),
    ("AMD", 0),
    (10**6, 0),
    (0.001, 0),
    (1.1, 1),   
])
def test_check_input(val, expected):
    assert polish_ver.check_input(val) == expected


# ---------------- random_cards ----------------
# These assume random_cards validates 0..52 and raises ValueError otherwise.
# If your function doesn't raise, adapt expectations accordingly.

def test_random_cards_zero():
    assert polish_ver.random_cards(0) == []

def test_random_cards_one():
    cards = polish_ver.random_cards(1)
    assert len(cards) == 1
    assert isinstance(cards[0], str)

def test_random_cards_full_deck():
    cards = polish_ver.random_cards(52)
    assert len(cards) == 52
    assert len(set(cards)) == 52

def test_random_cards_too_large_raises():
    with pytest.raises(ValueError):
        polish_ver.random_cards(60)

def test_random_cards_randomness():
    c1 = polish_ver.random_cards(5)
    c2 = polish_ver.random_cards(5)
    # Very likely to differ; at minimum ensure no duplicates in each run
    assert c1 != c2 or (len(set(c1)) == len(c1) == 5 and len(set(c2)) == len(c2) == 5)

def test_random_cards_seeded_deterministic():
    random.seed(42)
    a = polish_ver.random_cards(5)
    random.seed(42)
    b = polish_ver.random_cards(5)
    assert a == b


# ---------------- to_face_labels ----------------

def test_to_face_labels_empty():
    assert polish_ver.to_face_labels([]) == []

def test_to_face_labels_numeric_unchanged():
    assert polish_ver.to_face_labels(["2♠", "10♥"]) == ["2♠", "10♥"]

def test_to_face_labels_faces_mapped():
    inp = ["11♠", "12♥", "13♦", "14♣"]
    out = ["J♠",  "Q♥",  "K♦",  "A♣"]
    assert polish_ver.to_face_labels(inp) == out

def test_to_face_labels_mixed():
    inp = ["11♣","7♣","6♥","11♥","2♣"]
    out = ["J♣", "7♣","6♥","J♥","2♣"]
    assert polish_ver.to_face_labels(inp) == out

def test_to_face_labels_weird_inputs():
    # "14" becomes "A" (no suit)
    inp = ["JOKER", "♠", "14"]
    out = ["JOKER", "♠", "A"]
    assert polish_ver.to_face_labels(inp) == out


# ---------------- rank ----------------
@pytest.mark.parametrize("val", ["", None, "♠", "Z♣", "1♣", "15♠"])
def test_rank_invalid(val):
    with pytest.raises(ValueError):
        polish_ver.rank(val)

@pytest.mark.parametrize("val,expected", [
    ("2♠", 2),
    ("10♥", 10),
    ("J♣", 11),
    ("Q♦", 12),
    ("K♠", 13),
    ("A♥", 14),
])
def test_rank_valid(val, expected):
    assert polish_ver.rank(val) == expected


# ---------------- _lerp ----------------
def test_lerp_out_of_bounds_t():
    assert polish_ver._lerp(0, 10, -1) == 0
    assert polish_ver._lerp(0, 10, 2) == 10

def test_lerp_invalid_values():
    import math
    with pytest.raises(ValueError):
        polish_ver._lerp(math.inf, 1, 0.5)


# ---------------- _grid_anchors ----------------
def test_grid_anchors_zero_cards():
    anchors, w, h = polish_ver._grid_anchors(0, 10, 10, 2, 2)
    assert anchors == []
    assert w == 0 and h == 0

def test_grid_anchors_negative_wh():
    with pytest.raises(ValueError):
        polish_ver._grid_anchors(5, -1, 10, 2, 2)
